<!doctype html>
<html lang="vi" class="h-100">

<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

  <!-- Bootstrap CSS -->
  <link rel="stylesheet" href="/assets/vendor/bootstrap/css/bootstrap.min.css" type="text/css" />
  <!-- Font awesome -->
  <link rel="stylesheet" href="/assets/vendor/font-awesome/css/font-awesome.min.css" type="text/css" />

  <!-- Custom css - Các file css do chúng ta tự viết -->
  <link rel="stylesheet" href="/assets/frontend/css/style.css" type="text/css" />

  <!-- Block title - Đục lỗ trên giao diện bố cục chung, đặt tên là `title` -->
  <title> Tri thức - Tri thức cơ bản về du lịch |
    {% block title %}
    {% endblock %}
  </title>
  <!-- End block title -->

  <!-- Block custom-styles - Đục lỗ trên giao diện bố cục chung, đặt tên là `custom-styles` -->
  {% block customstyles %}
  {% endblock %}
  <!-- End block custom-styles -->
</head>

<body>
  <!-- header -->
  {{ include('frontend/layouts/includes/header.html.twig') }}
  <!-- end header -->
  <main role="main">
    <!-- Block content - Đục lỗ trên giao diện bố cục chung, đặt tên là `content` -->
    {% block content %}
    {% endblock %}
    <!-- End block content -->
  </main>

  <!-- footer -->
  {{ include('frontend/layouts/includes/footer.html.twig') }}
  <!-- end footer -->

  <!-- Optional JavaScript -->
  <!-- jQuery first, then Popper.js, then Bootstrap JS -->
  <script src="/assets/vendor/jquery/jquery.min.js"></script>
  <script src="/assets/vendor/popperjs/popper.min.js"></script>
  <script src="/assets/vendor/bootstrap/js/bootstrap.min.js"></script>
  <script src="/assets/vendor/feather/feather.min.js"></script>

  <!-- Custom script - Các file js do mình tự viết -->
  <script src="/assets/frontend/js/app.js"></script>

  <!-- Block custom-scripts - Đục lỗ trên giao diện bố cục chung, đặt tên là `custom-scripts` -->
  {% block customscripts %}
  {% endblock %}
  <!-- End block custom-scripts -->
</body>

</html>
<nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
    <div class="container">
        <a class="navbar-brand" href="https://trithuc.vn">Tri Thức</a>
        <div class="navbar-collapse collapse" id="navbarCollapse" style="">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                    <a class="nav-link" href="/">Trang chủ <span class="sr-only">(current)</span></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/backend/pages/dashboard.php">Quản trị</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/frontend/product/list.php">Sản phẩm</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/frontend/pages/about.php">Giới thiệu</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="/frontend/pages/contact.php">Liên hệ</a>
                </li>
            </ul>
            <form class="form-inline mt-2 mt-md-0" method="get" action="/frontend/product/search.php">
                <input class="form-control mr-sm-2" type="text" placeholder="Tìm kiếm" aria-label="Search"
                    name="keyword_tensanpham">
                <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Tìm kiếm</button>
            </form>
        </div>
        <ul class="navbar-nav px-3">
            <li class="nav-item text-nowrap">
                <a class="nav-link" href="/frontend/checkout/cart.php">Giỏ hàng</a>
            </li>
            <li class="nav-item text-nowrap">
                {% if session['email'] %}
                <!-- Nếu đã đăng nhập thì hiển thị Thông tin Tài khoản -->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                      Cá nhân
                    </a>
                    <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                      <a class="dropdown-item" href="#">Thông tin</a>
                      <a class="dropdown-item" href="#">Danh sách Đặt hàng</a>
                      <div class="dropdown-divider"></div>
                      <a class="dropdown-item" href="/frontend/auth/logout.php">Đăng xuất</a>
                    </div>
                </li>
                {% else %}
                <!-- Nếu chưa đăng nhập thì hiển thị nút Đăng nhập -->
                <a class="nav-link" href="/frontend/auth/login.php">Đăng nhập</a>
                {% endif %}
            </li>
        </ul>
    </div>
</nav>
<footer class="footer mt-auto py-3">
    <div class="container">
        <span>Bản quyền &copy; bởi <a href="https://trithuc.vn">Tri Thức </a> - <script>document.write(new Date().getFullYear());</script>.</span>
        <span class="text-muted">Hành trang tới Tương lai</span>

        <p class="float-right">
            <a href="#">Về đầu trang</a>
        </p>
    </div>
</footer>
