# ChungMinh SMP — bộ mod + config client

**Tải:** https://github.com/luongminhduc-hittake/chungminh-smp-client/releases/download/v1/ChungMinhSMP-client.zip

Copy vào thư mục game (`.minecraft` hoặc instance PrismLauncher/MultiMC).

## Yêu cầu

| | |
|---|---|
| Minecraft | **26.3** (đúng bản, không phải 26.3.x khác) |
| Fabric Loader | `0.20.1` hoặc mới hơn |
| Java | **25** (bắt buộc — CIT Resewn khai báo `java >= 25`) |
| RAM | cấp **4 GB** cho game (mặc định 2 GB hay thiếu) |

## Cài

1. Cài **Fabric Loader 0.20.1+** cho Minecraft **26.3**, dùng Java 25.
2. Copy **nội dung** thư mục này vào `.minecraft/`:
   - `mods/` → 29 mod
   - `config/` → 31 file, đã cấu hình sẵn
   - `shaderpacks/` → Mellow v3.4.1a
   - `options.txt` → setting đồ họa đã tối ưu
   - `servers.dat` → server đã thêm sẵn
3. Nếu là **macOS**, copy thêm 2 mod trong `mods-macos-only/` vào `mods/`.
4. Vào game → **Multiplayer** → `ChungMinh SMP`.

Lần join đầu sẽ tải resource pack (~12 MB) từ GitHub. Bấm **Yes/Proceed** khi được hỏi.

## Setting đồ họa đã đặt sẵn

| Setting | Giá trị | Lý do |
|---|---|---|
| `renderDistance` | 12 | Cân bằng giữa tầm nhìn và FPS |
| `simulationDistance` | 5 | Giảm tick, đỡ CPU |
| `maxFps` | 120 | Không giới hạn cứng 60 |
| `particles` | 0 (minimal) | Particle nhiều làm tụt FPS |
| `renderClouds` | false | Cloud 3D tốn fill-rate |
| `mipmapLevels` | 4 | Texture 16x mượt ở xa |
| `ao` | true | Ambient occlusion — bật vì pack cần |
| `entityShadows` | true | Bóng entity |
| `graphicsPreset` | custom | Giữ đúng combo trên |
| `guiScale` | 0 (auto) | Tự theo độ phân giải |
| `fullscreen` | false | Để Cậu tự chọn |
| `mouseSensitivity` | 0.5 | Mặc định |
| `fov` | 0.5 (~70°) | Mặc định, không gây say |

Mưa/snow, vignette, damage tilt giữ mặc định.

## Config mod đã tinh chỉnh

- **MoreCulling**: `leavesCullingMode = "FAST"` — lá Better Leaves là model cross
  5 element nên culling `DEFAULT` hay làm mất mặt lá.
- **BBE**: `misc.sign_text_distance = 7` — giảm từ 16, đỡ tốn khi nhiều biển.
- **Continuity**: bật cả `connected_textures` và `emissive_textures`.
- **EMF**: `allowedCEM = ALL`, `asmMaths = true` (nhanh hơn expression tree).
- **ETF**: giữ nguyên, đã đúng cho pack.
- **CIT Resewn**: `broken_paths = false` — **không cần bật**; pack dùng `./parent`
  nhưng fork này resolve được (đã kiểm chứng qua log, 0 lỗi broken path).
- **Sodium**: `chunk_build_defer_mode = ALWAYS`, `animate_only_visible_textures = true`.

## Mod

| Mod | Tên | Version | Việc |
|---|---|---|---|
| `immediatelyfast` | ImmediatelyFast | `1.17.1+26.3` | Cache buffer upload, giảm CPU cho GPU |
| `betterblockentities` | BBE | `1.4.0+mc26.3` | Tối ưu render chest/shulker/sign/banner |
| `capes` | Capes | `1.5.10+26.3` | Hiện cape của người chơi |
| `citresewn` | CIT Resewn fork | `1.2.2-fork.14+26.3` | CIT — item texture tuỳ biến (OptiFine format) |
| `cloth-config` | Cloth Config v26.3 | `26.3.159` | Thư viện config GUI |
| `continuity` | Continuity | `3.0.1+26.3` | CTM + emissive block (OptiFine format) |
| `elytratrails` | Elytra Contrails | `1.6.9-26.3` | Vệt elytra |
| `entity_model_features` | Entity Model Features | `3.3.12` | CEM — model/anim mob (OptiFine format) |
| `entity_texture_features` | Entity Texture Features | `7.2.6` | Random entity texture + emissive entity |
| `entityculling` | EntityCulling | `1.11.3` | Không render entity bị che |
| `fabric-api` | Fabric API | `0.165.0+26.3` | API nền của Fabric |
| `fabric-language-kotlin` | Fabric Language Kotlin | `1.14.2+kotlin.2.4.21` | Kotlin runtime |
| `ferritecore` | FerriteCore | `9.0.0` | Giảm RAM model/item |
| `iris` | Iris | `1.11.7+mc26.3` | Shader pack |
| `lambdynlights` | LambDynamicLights | `4.13.0+26.3` |  |
| `lithium` | Lithium | `0.26.2+mc26.3` | Tối ưu tick server-side logic |
| `mr_ly_clumps` | Clumps | `1-v1.1.0` | Gộp XP orb |
| `modmenu` | Mod Menu | `21.0.0` | Danh sách mod |
| `moreculling` | More Culling | `1.9.0` | Cull face ẩn (leaves, glass...) |
| `polytone` | Polytone | `26.3-6.8.6` | Colormap + color.properties (OptiFine format) |
| `reeses-sodium-options` | Reese's Sodium Options | `2.2.6-beta.1+mc26.3` | Menu option Sodium mở rộng |
| `shulkerboxtooltip` | Shulker Box Tooltip | `5.4.3+26.3` | Xem trước nội dung shulker |
| `simplehudenhanced` | Simple Hud Enhanced | `4.7.5` | HUD: toạ độ, giờ, armor |
| `skinlayers3d` | 3d-Skin-Layers | `1.11.4` | Skin 3D layer |
| `sodium-extra` | Sodium Extra | `0.9.6-beta.1+mc26.3` | Option Sodium thêm |
| `sodium` | Sodium | `0.9.3-beta.1+mc26.3` | Render engine |
| `voicechat` | Simple Voice Chat | `2.6.26+26.3` | Voice chat proximity |
| `yet_another_config_lib_v3` | YetAnotherConfigLib | `3.9.7+26.3-fabric` | Thư viện config GUI |
| `zoomify` | Zoomify | `2.17.0+mc26.3` | Zoom (C) |

## Lưu ý

**Voice chat**: mod có sẵn nhưng server **không** forward UDP qua VPS NAT, nên voice
chat sẽ **không hoạt động** khi chơi qua `103.249.117.232:26889`. Vẫn dùng được nếu
chơi trong LAN.

**Shader**: Iris + Mellow v3.4.1a đã bật sẵn. Nếu máy yếu, tắt trong
`Options → Video Settings → Shader Packs`.

**Resource pack**: server đặt `require-resource-pack = true`, nên pack tải tự động
và không thể bỏ qua. Pack 55% là định dạng OptiFine — đó là lý do cần 5 mod
EMF / ETF / Continuity / CIT Resewn / Polytone. Không cài đủ thì pack vẫn chạy
nhưng mất CTM (viền nối block), CIT (item custom), CEM (mob animation).

## Chưa tối ưu được

- **Keybind**: giữ mặc định vanilla. Ai quen phím khác tự đổi, không ảnh hưởng.
- **`language`**: `en_us`. Muốn tiếng Việt thì đổi trong Options (nếu pack có locale).
- **`servers.dat`** chỉ chứa `103.249.117.232` (địa chỉ công khai). Ai chơi cùng LAN
  với server thì tự thêm IP nội bộ — tôi cố tình không đưa IP LAN vào file phát tán.
