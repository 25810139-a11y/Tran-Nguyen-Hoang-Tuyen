
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TUYẾN DEPTRAI | Fashion Store</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
    
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 85px;
    }

    body {
      font-family: Arial, sans-serif;
      color: #111;
      background: #fff;
      line-height: 1.6;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    button {
      cursor: pointer;
      font: inherit;
    }

    .container {
      width: min(1100px, 92%);
      margin: auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 10;
      background: white;
      border-bottom: 1px solid #eee;
    }

    .navbar {
      min-height: 70px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }

    .logo {
      font-size: 23px;
      font-weight: 900;
      white-space: nowrap;
    }

    .logo span {
      font-weight: 400;
    }

    nav {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
    }

    nav a {
      font-size: 14px;
      font-weight: bold;
    }

    nav a:hover {
      color: #777;
    }

    #cart-count {
      display: inline-block;
      min-width: 20px;
      padding: 0 5px;
      border-radius: 20px;
      color: white;
      background: #111;
      text-align: center;
    }

    .hero {
      background: #111;
      color: white;
      padding: 95px 0;
    }

    .eyebrow {
      margin-bottom: 12px;
      color: #888;
      font-size: 12px;
      font-weight: bold;
      letter-spacing: 2px;
    }

    .hero .eyebrow {
      color: #ccc;
    }

    .hero h1 {
      max-width: 750px;
      margin-bottom: 18px;
      font-size: clamp(34px, 6vw, 58px);
      line-height: 1.15;
    }

    .hero p:not(.eyebrow) {
      max-width: 550px;
      margin-bottom: 25px;
      color: #ddd;
    }

    .btn {
      display: inline-block;
      padding: 12px 20px;
      border: 1px solid #111;
      background: #111;
      color: white;
      font-weight: bold;
      font-size: 14px;
      text-align: center;
    }

    .btn:hover {
      opacity: .8;
    }

    .btn-white {
      background: white;
      color: #111;
      border-color: white;
    }

    section {
      padding: 65px 0;
    }

    .section-title {
      margin-bottom: 28px;
    }

    .section-title h2 {
      font-size: clamp(26px, 4vw, 36px);
      line-height: 1.3;
    }

    .muted {
      color: #666;
    }

    /* SẢN PHẨM */

    .products {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
    }

    .product {
      border: 1px solid #e5e5e5;
      overflow: hidden;
      background: white;
    }

    .product-image {
      aspect-ratio: 4 / 4;
      display: grid;
      place-items: center;
      background: #f3f3f3;
      color: #888;
      font-size: 14px;
      overflow: hidden;
    }

    .product-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .product-info {
      padding: 16px;
    }

    .category {
      color: #777;
      font-size: 12px;
      margin-bottom: 5px;
    }

    .product h3 {
      margin-bottom: 8px;
      font-size: 17px;
    }

    .description {
      min-height: 45px;
      margin-bottom: 12px;
      color: #666;
      font-size: 13px;
    }

    .price {
      margin-bottom: 14px;
      font-size: 17px;
      font-weight: 800;
    }

    .product .btn {
      width: 100%;
    }

    /* GIỎ HÀNG */

    #cart {
      background: #f6f6f6;
    }

    .cart-item {
      display: grid;
      grid-template-columns: 85px minmax(0, 1fr);
      gap: 15px;
      padding: 15px;
      margin-bottom: 12px;
      border: 1px solid #e5e5e5;
      background: white;
    }

    .cart-image {
      width: 85px;
      height: 100px;
      display: grid;
      place-items: center;
      overflow: hidden;
      background: #f3f3f3;
    }

    .cart-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .cart-item h3 {
      font-size: 16px;
    }

    .cart-item p {
      margin: 3px 0;
      color: #666;
      font-size: 13px;
    }

    .cart-controls {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 10px;
      margin-top: 10px;
    }

    .qty-btn {
      width: 32px;
      height: 32px;
      border: 1px solid #ddd;
      background: white;
    }

    .remove-btn {
      border: none;
      background: none;
      color: #555;
      text-decoration: underline;
    }

    .cart-summary {
      margin-top: 20px;
      padding: 22px;
      border: 1px solid #ddd;
      background: white;
    }

    .summary-row {
      display: flex;
      justify-content: space-between;
      gap: 15px;
      margin: 10px 0;
    }

    .total {
      padding-top: 12px;
      border-top: 1px solid #ddd;
      font-size: 18px;
      font-weight: bold;
    }

    .empty {
      padding: 35px 15px;
      background: white;
      border: 1px solid #ddd;
      text-align: center;
    }

    .empty p {
      margin: 8px 0 18px;
      color: #666;
    }

    /* GIỚI THIỆU VÀ LIÊN HỆ */

    #about {
      background: #eee;
      text-align: center;
    }

    #about p:not(.eyebrow) {
      max-width: 650px;
      margin: 15px auto 22px;
      color: #555;
    }

    .contact-card {
      max-width: 600px;
      padding: 25px;
      border: 1px solid #ddd;
      background: #f7f7f7;
    }

    .contact-card p {
      margin-top: 8px;
      color: #555;
    }

    footer {
      padding: 25px 0;
      background: #111;
      color: white;
      text-align: center;
    }

    footer p {
      margin: 5px 0;
      color: #ccc;
      font-size: 13px;
    }

    @media (max-width: 700px) {
      .navbar {
        align-items: flex-start;
        flex-direction: column;
        padding: 15px 0;
        gap: 10px;
      }

      nav {
        gap: 10px 16px;
      }

      nav a {
        font-size: 13px;
      }

      .hero {
        padding: 65px 0;
      }

      section {
        padding: 45px 0;
      }

      .products {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 12px;
      }

      .product-info {
        padding: 10px;
      }

      .product h3 {
        font-size: 14px;
      }

      .description {
        min-height: 0;
      }

      .product .btn {
        padding: 10px 5px;
        font-size: 12px;
      }
    }

    @media (max-width: 360px) {
      nav {
        gap: 8px;
      }

      nav a {
        font-size: 12px;
      }

      .products {
        gap: 8px;
      }
    }
  </style>
</head>

<body>

  <!-- MENU -->
  <header>
    <div class="container navbar">
      <a class="logo" href="#home">TUYẾN <span>DEPTRAI</span></a>

      <nav>
        <a href="#home">Trang chủ</a>
        <a href="#products">Sản phẩm</a>
        <a href="#cart">Giỏ hàng (<span id="cart-count">0</span>)</a>
        <a href="#about">Giới thiệu</a>
        <a href="#contact">Liên hệ</a>
      </nav>
    </div>
  </header>

  <main>

    <!-- BANNER -->
    <section class="hero" id="home">
      <div class="container">
        <p class="eyebrow">TUYẾN DEPTRAI FASHION STORE</p>
        <h1>Mặc chất riêng.<br>Tự tin mỗi ngày.</h1>
        <p>
          Khám phá thời trang trẻ trung, hiện đại
          và tìm phong cách dành riêng cho bạn.
        </p>
        <a class="btn btn-white" href="#products">
          MUA SẮM NGAY
        </a>
      </div>
    </section>

    <!-- SẢN PHẨM -->
    <section id="products">
      <div class="container">
        <div class="section-title">
          <p class="eyebrow">BỘ SƯU TẬP</p>
          <h2>Sản phẩm nổi bật</h2>
          <p class="muted">Chọn món đồ bạn yêu thích.</p>
        </div>

        <div class="products" id="product-list"></div>
      </div>
    </section>

    <!-- GIỎ HÀNG -->
    <section id="cart">
      <div class="container">
        <div class="section-title">
          <p class="eyebrow">YOUR CART</p>
          <h2>Giỏ hàng của bạn</h2>
          <p class="muted">Kiểm tra sản phẩm trước khi mua.</p>
        </div>

        <div id="cart-content"></div>
      </div>
    </section>

    <!-- GIỚI THIỆU -->
    <section id="about">
      <div class="container">
        <p class="eyebrow">ABOUT US</p>
        <h2>Về TUYẾN DEPTRAI</h2>
        <p>
          Chúng tôi hướng đến phong cách thời trang đơn giản,
          trẻ trung và dễ phối đồ. Hãy tự tin thể hiện cá tính
          qua những lựa chọn của riêng bạn.
        </p>
        <a class="btn" href="#products">Khám phá sản phẩm</a>
      </div>
    </section>

    <!-- LIÊN HỆ -->
    <section id="contact">
      <div class="container">
        <div class="section-title">
          <p class="eyebrow">CONTACT</p>
          <h2>Liên hệ với chúng tôi</h2>
        </div>

        <div class="contact-card">
          <h3>TUYẾN DEPTRAI</h3>
          <p>Thời trang dành cho người trẻ.</p>
          <p><strong>Điện thoại:</strong> Chưa cập nhật</p>
          <p><strong>Email:</strong> Chưa cập nhật</p>
          <p><strong>Địa chỉ:</strong> Chưa cập nhật</p>
        </div>
      </div>
    </section>

  </main>

  <footer>
    <div class="container">
      <h3>TUYẾN DEPTRAI</h3>
      <p>Phong cách của bạn, lựa chọn của bạn.</p>
      <p>© 2026 TUYẾN DEPTRAI. Website đồ án Lập trình Web.</p>
    </div>
  </footer>

  <script>
    // DANH SÁCH SẢN PHẨM MẪU
    const products = [
      {
        id: 1,
        name: "Áo thun basic đen",
        category: "ÁO THUN",
        price: 159000,
        description: "Tối giản, trẻ trung, dễ phối đồ.",
        image: ""
      },
      {
        id: 2,
        name: "Áo thun trắng",
        category: "ÁO THUN",
        price: 159000,
        description: "Phong cách năng động mỗi ngày.",
        image: ""
      },
      {
        id: 3,
        name: "Áo sơ mi casual",
        category: "ÁO SƠ MI",
        price: 259000,
        description: "Thanh lịch, hiện đại, dễ mặc.",
        image: ""
      },
      {
        id: 4,
        name: "Quần jeans xanh",
        category: "QUẦN",
        price: 329000,
        description: "Dễ phối cùng nhiều kiểu áo.",
        image: ""
      },
      {
        id: 5,
        name: "Giày sneaker trắng",
        category: "GIÀY DÉP",
        price: 459000,
        description: "Trẻ trung, phù hợp đi chơi.",
        image: ""
      },
      {
        id: 6,
        name: "Túi đeo chéo",
        category: "PHỤ KIỆN",
        price: 199000,
        description: "Gọn gàng, tiện dụng mỗi ngày.",
        image: ""
      }
    ];

    const CART_KEY = "tuyen-deptrai-cart";

    function money(value) {
      return Number(value).toLocaleString("vi-VN") + "đ";
    }

    function loadCart() {
      try {
        const cart = JSON.parse(localStorage.getItem(CART_KEY) || "[]");
        return Array.isArray(cart) ? cart : [];
      } catch (error) {
        return [];
      }
    }

    function saveCart(cart) {
      localStorage.setItem(CART_KEY, JSON.stringify(cart));
      updateCartCount();
    }

    function updateCartCount() {
      const count = loadCart().reduce((sum, item) => {
        return sum + Math.max(0, Number(item.quantity) || 0);
      }, 0);

      document.getElementById("cart-count").textContent = count;
    }

    // HIỂN THỊ SẢN PHẨM
    function renderProducts() {
      const list = document.getElementById("product-list");

      list.innerHTML = products.map(product => `
        <article class="product">
          <div class="product-image">
            ${
              product.image
                ? `<img src="${product.image}" alt="${product.name}">`
                : `<span>Ảnh sản phẩm</span>`
            }
          </div>

          <div class="product-info">
            <p class="category">${product.category}</p>
            <h3>${product.name}</h3>
            <p class="description">${product.description}</p>
            <p class="price">${money(product.price)}</p>

            <button
              class="btn add-btn"
              type="button"
              data-id="${product.id}"
            >
              Thêm vào giỏ
            </button>
          </div>
        </article>
      `).join("");
    }

    // THÊM SẢN PHẨM
    function addToCart(id) {
      const product = products.find(item => item.id === id);

      if (!product) return;

      const cart = loadCart();
      const existing = cart.find(item => item.id === id);

      if (existing) {
        existing.quantity += 1;
      } else {
        cart.push({
          id: product.id,
          name: product.name,
          price: product.price,
          quantity: 1
        });
      }

      saveCart(cart);
      renderCart();
    }

    // HIỂN THỊ GIỎ HÀNG
    function renderCart() {
      const container = document.getElementById("cart-content");
      const cart = loadCart().filter(item => {
        return products.some(product => product.id === item.id) &&
          Number(item.quantity) > 0;
      });

      if (cart.length === 0) {
        container.innerHTML = `
          <div class="empty">
            <h3>Giỏ hàng đang trống</h3>
            <p>Hãy chọn sản phẩm bạn yêu thích nhé!</p>
            <a class="btn" href="#products">Xem sản phẩm</a>
          </div>
        `;
        return;
      }

      const total = cart.reduce((sum, item) => {
        return sum + item.price * item.quantity;
      }, 0);

      container.innerHTML = `
        <div>
          ${cart.map(item => {
            const product = products.find(p => p.id === item.id);

            return `
              <article class="cart-item">
                <div class="cart-image">
                  ${
                    product.image
                      ? `<img src="${product.image}" alt="${product.name}">`
                      : `<span>Ảnh</span>`
                  }
                </div>

                <div>
                  <h3>${product.name}</h3>
                  <p>Đơn giá: ${money(product.price)}</p>
                  <p>Thành tiền: <strong>${money(product.price * item.quantity)}</strong></p>

                  <div class="cart-controls">
                    <button class="qty-btn" data-action="minus" data-id="${item.id}" aria-label="Giảm số lượng">−</button>
                    <span>${item.quantity}</span>
                    <button class="qty-btn" data-action="plus" data-id="${item.id}" aria-label="Tăng số lượng">+</button>
                    <button class="remove-btn" data-action="remove" data-id="${item.id}">Xóa</button>
                  </div>
                </div>
              </article>
            `;
          }).join("")}
        </div>

        <div class="cart-summary">
          <h3>Tóm tắt đơn hàng</h3>

          <div class="summary-row">
            <span>Số loại sản phẩm</span>
            <span>${cart.length}</span>
          </div>

          <div class="summary-row">
            <span>Tổng số lượng</span>
            <span>${cart.reduce((sum, item) => sum + item.quantity, 0)}</span>
          </div>

          <div class="summary-row total">
            <span>Tổng tiền</span>
            <span>${money(total)}</span>
          </div>

          <p class="muted" style="font-size:13px; margin:12px 0">
            Đây là giỏ hàng mô phỏng, chưa có thanh toán thật.
          </p>

          <a class="btn" href="#products">Tiếp tục mua sắm</a>
        </div>
      `;
    }

    // XỬ LÝ CÁC NÚT BẤM
    document.addEventListener("click", function(event) {
      const addButton = event.target.closest(".add-btn");

      if (addButton) {
        addToCart(Number(addButton.dataset.id));
        return;
      }

      const actionButton = event.target.closest("[data-action]");

      if (!actionButton) return;

      const id = Number(actionButton.dataset.id);
      const action = actionButton.dataset.action;
      const cart = loadCart();
      const item = cart.find(product => product.id === id);

      if (!item) return;

      if (action === "plus") {
        item.quantity += 1;
      } else if (action === "minus") {
        item.quantity -= 1;
      } else if (action === "remove") {
        saveCart(cart.filter(product => product.id !== id));
        renderCart();
        return;
      }

      saveCart(cart.filter(product => product.quantity > 0));
      renderCart();
    });

    // KHỞI ĐỘNG WEBSITE
    renderProducts();
    updateCartCount();
    renderCart();
  </script>

</body>
</html>
