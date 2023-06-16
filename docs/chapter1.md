# K8S调度器

## 污点与容忍

3种容忍类型：

`NoSchedule`：K8S不会把Pod调度到具有该污点的Node上

`PreferNoSchedule`：K8S将尽量避免将Pod调度到具有该污点的Node上

`NoExcute`：K8S不会把Pod调度到具有该污点的Node上，且会把已经在Node上运行的Pod干掉

### 给node设置污点（taints），给pod设置容忍（tolerant）

```bash

```