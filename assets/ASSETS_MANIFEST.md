# 已下载素材清单（2026-11-17，全部 CC0 / MIT）

Qoder 下载失败（TLS 握手错误），以下文件由开发者手动下载并放入。请 Qoder 据此解压整理、校验、编写 `public/assets/CREDITS.md`。

## HDRI
| 文件 | 用途 | 来源 | 协议 |
|---|---|---|---|
| `hdri/venice_sunset_1k.hdr` | 环境光照（傍晚） | Poly Haven：https://polyhaven.com/a/venice_sunset | CC0 |

## PBR 材质（ambientCG，1K-JPG 压缩包，未解压）
| 文件 | 用途 | 来源 | 协议 |
|---|---|---|---|
| `downloads/Bricks061_1K-JPG.zip` | 灰砖墙（斋字楼外墙） | https://ambientcg.com/a/Bricks061 | CC0 |
| `downloads/PaintedWood003_1K-JPG.zip` | 红漆木（柱子、门窗）。颜色偏艳，使用时把漫反射颜色乘以 #a3322b 一类的暗朱红再降饱和度 | https://ambientcg.com/a/PaintedWood003 | CC0 |
| `downloads/Rock030_1K-JPG.zip` | 石材（石舫、台基、驳岸、假山石、华表底座） | https://ambientcg.com/a/Rock030 | CC0 |
| `downloads/PavingStones136_1K-JPG.zip` | 石板路 | https://ambientcg.com/a/PavingStones136 | CC0 |
| `downloads/Ground068_1K-JPG.zip` | 土路、树下裸土 | https://ambientcg.com/a/Ground068 | CC0 |
| `downloads/Grass004_1K-JPG.zip` | 草地 | https://ambientcg.com/a/Grass004 | CC0 |
| `downloads/Concrete034_1K-JPG.zip` | 浅色涂料墙（赛区外的现代建筑） | https://ambientcg.com/a/Concrete034 | CC0 |
| `downloads/RoofingTiles015A_1K-JPG.zip` | 屋面备选（平板方瓦，不如下面的灰瓦像中式屋顶） | https://ambientcg.com/a/RoofingTiles015A | CC0 |

## 屋面主材质（Poly Haven，已是散文件）
| 文件夹 | 用途 | 来源 | 协议 |
|---|---|---|---|
| `downloads/polyhaven_grey_roof_tiles/`（diff / nor_gl / rough / ao / disp，1K） | **中式灰瓦屋面主材质**（竖向瓦垄，带风化） | https://polyhaven.com/a/grey_roof_tiles | CC0 |

## 水面
| 文件 | 用途 | 来源 | 协议 |
|---|---|---|---|
| `water/waternormals.jpg` | 未名湖水面法线贴图（配合 three/addons 的 Water.js） | three.js 仓库 r180 examples/textures | MIT（three.js） |

## 说明
- 法线贴图：ambientCG 包里用 `NormalGL`，Poly Haven 用 `nor_gl`（OpenGL 约定，three.js 直接可用）。
- 运行时不要再访问任何外部网站。

## 植被数据
| 文件 | 用途 | 来源 | 协议 |
|---|---|---|---|
| `../data/vegetation.json`、`../data/canopy_height.png` | 真实树木位置、树高、树冠半径、灌木区 | Meta & World Resources Institute, High Resolution Canopy Height Maps（2024），1 米分辨率，切片 132100103 | CC BY 4.0（必须署名） |
