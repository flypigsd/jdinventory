# jdinventory

采销库存看板 - 上传采销大表，自动生成现货库存 & 在途库存视图。

## 部署

- **线上地址**: https://flypigsd.github.io/jdinventory/
- **GitHub Pages** 自动部署，push 到 main 分支后 1-2 分钟生效
- 工作文件同步副本: `C:\Users\zhuzh\Desktop\采销库存看板.html`（与仓库 `index.html` 需保持一致）

## 部署命令

```bash
git add index.html && git commit -m "<描述>" && git push
```

## 数据列映射

| 内部字段 | Excel 列名 |
|---------|-----------|
| spotQty | 全国现货库存 |
| inTransitQty | 全国采购未到货 |
| purchasePrice | 全国仓报价 |
| spotCost | 全国现货库存成本 |
| out7d | 近7天销量 |
| turnover | 全国数量周转 |

## 金额计算规则

- **现货库存金额** = 直接取 `全国现货库存成本` 列，不做乘法
- **在途金额** = `全国采购未到货` × `全国仓报价`
