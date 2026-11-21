# 本地素材来源与许可

整理日期：2026-11-17。运行时不访问外部素材网站。以下素材均由开发者下载，Qoder 仅解压、整理和校验；未使用来源不明的替代素材。

## HDRI

| 本地文件 | 名称 / 作者 | 来源 | 许可 | 下载日期 |
|---|---|---|---|---|
| `hdri/venice_sunset_1k.hdr` | Venice Sunset / Greg Zaal | https://polyhaven.com/a/venice_sunset | CC0 | 2026-11-17 |

HDRI 仅经 PMREM 用于环境光照，不作为场景背景。文件大小 1,440,400 字节，MD5 `a5ec4d30fc3421c214a17b208fb66d5f`，与 Poly Haven API 返回值一致。

## PBR 贴图

下列 ambientCG 素材均为 1K JPG，许可均为 CC0，下载日期均为 2026-11-17，作者/发布者标注为 ambientCG。

| 本地目录 | 素材 | 来源 | 用途 |
|---|---|---|---|
| `textures/roofing-alt/` | RoofingTiles015A | https://ambientcg.com/a/RoofingTiles015A | 备选屋面 |
| `textures/brick/` | Bricks061 | https://ambientcg.com/a/Bricks061 | 灰砖墙 |
| `textures/painted-wood/` | PaintedWood003 | https://ambientcg.com/a/PaintedWood003 | 暗朱红漆木，运行时降低饱和度 |
| `textures/stone/` | Rock030 | https://ambientcg.com/a/Rock030 | 石舫、台基、驳岸、假山石 |
| `textures/paving/` | PavingStones136 | https://ambientcg.com/a/PavingStones136 | 石板路 |
| `textures/ground/` | Ground068 | https://ambientcg.com/a/Ground068 | 土路与树下裸土 |
| `textures/grass/` | Grass004 | https://ambientcg.com/a/Grass004 | 草地 |
| `textures/concrete/` | Concrete034 | https://ambientcg.com/a/Concrete034 | 现代建筑涂料墙 |

保留 `Color`、`NormalGL`、`Roughness`、素材提供时的 `AmbientOcclusion` 与 `Displacement`。颜色贴图使用 sRGB；法线、粗糙度、AO、位移贴图保持线性。

| 本地目录 | 名称 / 作者 | 来源 | 许可 | 下载日期 |
|---|---|---|---|---|
| `textures/roof/` | Grey Roof Tiles / Poly Haven（作者信息见来源页） | https://polyhaven.com/a/grey_roof_tiles | CC0 | 2026-11-17 |

灰瓦保留 `diff`、`nor_gl`、`rough`、`ao`、`disp` 五类 1K JPG，是中式屋面的主材质。

## 水面法线

| 本地文件 | 名称 / 作者 | 来源 | 许可 | 下载日期 |
|---|---|---|---|---|
| `water/waternormals.jpg` | waternormals / three.js contributors | https://github.com/mrdoob/three.js/tree/r180/examples/textures | MIT（three.js） | 2026-11-17 |

three.js MIT 许可全文见 `node_modules/three/LICENSE`。水面法线保持线性色彩空间。

## 原始包

原始 ZIP 和散文件已移至项目根目录 `素材源包/` 留存，不由 Vite 提供，也不纳入运行时资源。该目录在 `.gitignore` 中排除，避免与已整理文件重复提交。

## 第 7 步运行时格式优化

保留上述原始 JPG，同时用 Pillow 从原始文件生成同分辨率 WebP 副本：反照率 quality=82、法线 quality=90、method=6。程序运行时加载 `.webp`，不改变素材内容、作者、来源或许可；原始 JPG 一并保留以便审核。共生成 44 个 WebP 文件，包含 `water/waternormals.webp`。

## 真实树冠数据

**树冠数据 © Meta & World Resources Institute, High Resolution Canopy Height Maps, CC BY 4.0**

- 本地文件：`public/data/vegetation.json` 与 `public/data/canopy_height.png`。
- 内容：866 个树木点位、树高、树冠半径、1354 片低矮植被，以及 747×731 灰度树冠高度图。
- 来源：Meta & World Resources Institute, High Resolution Canopy Height Maps（2024），1 米分辨率，切片 `132100103`。
- 协议：Creative Commons Attribution 4.0 International（CC BY 4.0），https://creativecommons.org/licenses/by/4.0/
- `species` 仅按位置推测，不代表实测树种；补种像素只用于恢复绿量，不声称是逐棵实测。

## 人物与动画

| 本地文件 | 名称 / 作者 | 来源 | 许可 | 下载日期 |
|---|---|---|---|---|
| `characters/animations.glb` | Universal Animation Library（Standard）/ Quaternius | https://quaternius.itch.io/universal-animation-library | CC0 1.0 | 2026-11-18 |

动画许可原文保存在 `LICENSE_UniversalAnimationLibrary.txt`。动画库保留 46 个官方动作，运行时通过 `vrm/retargetToVrm.js` 重定向到 VRM 骨骼。旧 Quaternius 基础人体和头发 GLB 已弃用并移除，不再进入首屏请求；当前人物外观见下面的 VRoid 条目。

## VRoid 人物（VRM）

下载日期 2026-11-19，由开发者登录 VRoid Hub 后手动下载。许可以模型页“使用条件”为准（模型内嵌的 `otherPermissionUrl` 与之一致）：下列模型都允许所有人作为头像使用、允许再分发、允许修改、允许个人商用。アコモン 的 4 个模型**不允许企业商用**（模型内嵌字段 `commercialUssageName: Disallow` 指的就是这一项），本作品为个人参赛作品，属于个人用途。发布的 VRM 是压缩版（`scripts/vrm-compress.py`：贴图缩到最长边 1024、不透明贴图转 JPEG、内嵌缩略图缩到 256、去掉表情形态键的法线；网格、骨骼、外观设计不变），属于各模型许可允许的“修改”；原件保存在不发布的 `素材原件/vrm/`。名牌等都是运行时叠加。

| 本地文件 | 模型 / 作者 | 来源 | 使用条件摘要 | 署名 |
|---|---|---|---|---|
| `characters/vrm/blazer_boy.vrm` | 制服男子 · ブレザー / アコモン | https://hub.vroid.com/en/characters/5867419587970160060/models/4433966118844651289 | 再分发、修改、个人商用允许；企业商用不允许 | 不需要（仍在此注明） |
| `characters/vrm/gakuran_boy.vrm` | 制服男子 · 学生服 / アコモン | https://hub.vroid.com/en/characters/5867419587970160060/models/264652388160130167 | 同上 | 不需要（仍在此注明） |
| `characters/vrm/jersey_boy.vrm` | ジャージ男子 / アコモン | https://hub.vroid.com/en/characters/1047416711131738223/models/7227236391939946135 | 同上 | 不需要（仍在此注明） |
| `characters/vrm/jersey_girl.vrm` | ジャージ女子 / アコモン | https://hub.vroid.com/en/characters/6579255163357991582/models/2279857613640208568 | 同上 | 不需要（仍在此注明） |
| `characters/vrm/yui_uniform.vrm` | 結 · 結_制服 / 明日太 | https://hub.vroid.com/en/characters/5063899628852192686/models/1129035981479608101 | 全部允许（含企业商用） | 不需要（仍在此注明） |

每个模型同目录下的 `*_thumb.png` 是从 VRM 内嵌缩略图提取的，统计见 `characters/vrm/统计.md`。

动画沿用上面的 Quaternius Universal Animation Library（CC0），运行时重定向到 VRM 骨骼。

## R3 脚步与动作声音（2026-11-20）

| 本地文件 | 名称 / 作者 | 来源 | 许可 | 使用与处理 |
|---|---|---|---|---|
| `audio/footsteps/grass_0..3.ogg`、`stone_0..3.ogg`、`turf_0..3.ogg` | Fantozzi's Footsteps (Grass/Sand & Stone) / Fantozzi（qubodup 切片提交） | https://opengameart.org/content/fantozzis-footsteps-grasssand-stone | CC0 1.0 | 草地、石板与人造草脚步；保留原包 OGG。人造草使用同包的 Sand 录音。 |
| `audio/footsteps/bush_0..3.ogg` | 20 Rustles of dry leaves / qubodup | https://opengameart.org/content/20-rustles-dry-leaves | CC0 1.0 | 灌木沙沙声及名牌扯动声；由原 FLAC 混为单声道、转为 24 kHz OGG Vorbis。 |
| `audio/footsteps/water_0..3.ogg` | 40 CC0 water / splash / slime SFX / rubberduck | https://opengameart.org/content/40-cc0-water-splash-slime-sfx | CC0 1.0 | 取 `splash_01..04.ogg` 作为水中脚步；混为单声道、转为 24 kHz OGG Vorbis。 |

许可原文：https://creativecommons.org/publicdomain/zero/1.0/ 。每类地面 4 个变体，R3 规则给定 `variant` 与 `pitch`，播放层不另造随机选择。喘气为代码生成的滤波噪声，心跳为代码合成的双音，不使用外部录音。

## 授权复核（2026-11-20，验收方）

逐个读了 5 个 VRM 内嵌的 meta（`allowedUserName`、`commercialUssageName`、`violentUssageName`、`otherPermissionUrl`），与上表和 VRoid Hub 使用条件一致。其余素材（Poly Haven / ambientCG / Quaternius / OpenGameArt 均 CC0；three.js、ez-tree MIT，ez-tree 树皮贴图来自 TextureCan 与 Poly Haven，均 CC0；OSM ODbL、树冠数据 CC BY 4.0 已在“关于”和页脚署名）可以使用。

需要注意的两条（アコモン 的 4 个模型：blazer_boy、gakuran_boy、jersey_boy、jersey_girl）：
1. **暴力表现：不允许**（`violent_expression=disallow`）。撕名牌本身是游戏对抗，但“出局时倒地死亡（Death01）”这类表现有风险。处理：出局改成不带伤害含义的动作（坐下 / 举手退场），不加击打类动作。最稳妥的做法是让学生用 VRoid Studio 自己捏 4 个原创角色替换（自己做的模型没有第三方条款限制，现有压缩和动作重定向流程直接可用）。
2. **企业商用：不允许**（个人商用、再分发、修改允许，署名不需要）。本作品是个人 / 学生参赛作品，属个人用途；但如果比赛条款要求把作品授权给主办方做商业用途，就和这一条冲突，需要看参赛协议里“作品使用授权”的条款；冲突时同样换成原创角色。
`yui_uniform.vrm`（明日太）全部允许（含暴力表现、企业商用）。

另：游戏不使用北大校徽、校名标识等官方标识（主菜单原有的“北大”印章已去掉）；`参考图/` 里的照片只作建模参考，不随作品发布，也不要用进宣发素材。
