# responsive-grid

Bài tập thực hành tại [CodeGym](https://codegym.vn): tái cấu trúc mã CSS của `responsive-grid` thành **SASS (SCSS)**.

## Cấu trúc thư mục

```
responsive-grid/
├── responsive_grid.htm      # Trang demo (đã bỏ toàn bộ style inline)
├── css/
│   └── style.css            # File CSS biên dịch từ SCSS
├── scss/
│   ├── style.scss           # File chính, chỉ @use các partial
│   ├── _variables.scss      # Màu sắc, kích thước, số cột, chiều cao các hàng
│   ├── _functions.scss      # column-width($span)
│   ├── _mixins.scss         # column(), plain-cell, band()
│   ├── _base.scss           # Reset (box-sizing)
│   └── _grid.scss           # Các thành phần của grid
└── package.json
```

## Kiến thức SASS đã áp dụng

- **Partials + `@use`**: chia mã thành các file nhỏ, mỗi file một nhiệm vụ.
- **Variables**: gom màu, khoảng cách, độ mờ, chiều cao vào `_variables.scss`.
- **Map + `@each`**: sinh các class `.gridwrapper--header`, `--body`, `--footer`, `--guide` từ map `$row-heights`.
- **Function**: `column-width($span)` tính chiều rộng theo số cột (`math.percentage(math.div($span, $grid-columns))`).
- **Mixin**: `column()`, `plain-cell`, `band()` để tái sử dụng các nhóm thuộc tính.
- **Nesting và `&`**: viết modifier theo kiểu BEM (`.gridcontent--header`, `.block--tall`, `&:first-child`, `&:last-child`).

## Cách biên dịch

```bash
npm install          # cài Sass (chỉ cần chạy một lần)
npm run sass         # biên dịch scss/style.scss -> css/style.css
npm run sass:watch   # tự biên dịch lại mỗi khi sửa file .scss
npm run sass:min     # xuất bản nén css/style.min.css
```

Sau đó mở `responsive_grid.htm` bằng trình duyệt và kéo thay đổi kích thước cửa sổ để xem grid co giãn.
