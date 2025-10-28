# 如何添加个人照片

## 方法 1: 直接放置照片文件

1. 将您的照片重命名为 `profile.jpg` (或 `profile.png`)
2. 放到 `images/` 目录下
3. 确保照片是正方形或接近正方形的比例(会自动裁剪为圆形)

```bash
# 推荐照片尺寸
# 至少 300x300 像素
# 最佳 500x500 或 800x800 像素
```

## 方法 2: 使用其他文件名

如果您的照片文件名不是 `profile.jpg`,可以修改 `_pages/about.md` 中的路径:

找到这一行:
```html
<img src="/images/profile.jpg" alt="Kehe Ye" ...>
```

改为:
```html
<img src="/images/your-photo-name.jpg" alt="Kehe Ye" ...>
```

## 方法 3: 使用外部链接

也可以使用外部图片链接(如 GitHub、图床等):

```html
<img src="https://example.com/your-photo.jpg" alt="Kehe Ye" ...>
```

## 当前照片位置

- 路径: `/images/profile.jpg`
- 显示: 右上角,圆形头像,150x150 像素
- 边框: 3px 浅灰色

## 如果没有照片

如果暂时没有照片,可以:

1. 使用占位图片(灰色圆圈)
2. 删除整个 `<div>` 图片部分
3. 使用 GitHub 头像:
   ```html
   <img src="https://github.com/keheye.png" alt="Kehe Ye" ...>
   ```

## 响应式设计

照片在手机端会自动:
- 移到名字上方
- 居中显示
- 保持圆形样式
