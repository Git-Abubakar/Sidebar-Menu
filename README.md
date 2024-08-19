- HTML 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sidebar Menu</title>
    <link rel="stylesheet" href="style.css">
    <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
</head>
<body>
    <nav class="sidebar">
    <div class="logo-menu">
        <h2 class="logo">AB-Github</h2>
        <i class='bx bx-menu toggle-btn'></i>
    </div>

    <ul class="list">
        <li class="list-item active">
            <a href="#">
                <i class='bx bx-grid-alt' ></i>
                <span class="link-name"  style="--i:1;">Dashboard</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-user' ></i>
                <span class="link-name"  style="--i:2;">User</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-chat' ></i>
                <span class="link-name"  style="--i:3;">Messages</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-pie-chart-alt-2' ></i>
                <span class="link-name" style="--i:4;">Analytics</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-folder' ></i>
                <span class="link-name" style="--i:5;">File Manager</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-cart-alt' ></i>
                <span class="link-name" style="--i:6;">Order</span>
                
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-heart' ></i>
                <span class="link-name" style="--i:7;">Saved</span>
            </a>
        </li>
        
        <li class="list-item">
            <a href="#">
                <i class='bx bx-cog' ></i>
                <span class="link-name" style="--i:8;">Setting</span>
            </a>
        </li>
    </ul>
</nav>

        <script src="script.js"></script>

</body>
</html>



-CSS 

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body {
    background: url(Back-Photo.jpg) no-repeat;
    background-size: cover;
    background-position: center;
    min-height: 100vh;
}

.sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 80px;
    height: 100%;
    background: transparent;
    backdrop-filter: blur(40px);
    padding: 6px 14px;
    transition: .5s;
    border-right: 2px solid rgba(255, 255, 255, .2);
    box-shadow: 0 0 10px rgba(0, 0, 0, .2);
}

.sidebar .logo-menu {
    display: flex;
    align-items: center;
    width: 100%;
    height: 70px;
    
}

.sidebar .logo-menu .logo {
    font-size: 25px;
    color: #fff;
    pointer-events: none;
    opacity: 0;
    transition: .3s;
}

.sidebar .logo-menu .toggle-btn
{
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 40px;
    height: 40px;
    
    font-size: 22px;
    color: #fff;
    text-align: center;
    line-height: 40px;
    cursor: pointer;
}

.sidebar .list {
    margin-top: 10px;

}

.list .list-item {
    list-style: none;
    width: 100%;
    height: 50px;
    /* background: slateblue; */
    margin: 5px 0;
    line-height: 50px;
}


.list .list-item a {
    font-size: 18px;
    color: #fff;
    text-decoration: none;
    display: flex;
    align-items: center;
    /* background: blue; */
    border-radius: 6px;
    transition: .5s;
    white-space: nowrap;
    
}


.list .list-item a i {
    min-width: 50px;
    height: 50px;
    /*background: salmon; */ 
    text-align: center;
    line-height: 50px;
    
}

.list .list-item.active a,
.list .list-item a:hover {
    background: rgba(255, 255, 255, .2);

}

.sidebar.active {
    width: 260px;
}

.sidebar.active .logo-menu .logo {
    opacity: 1;
    transition-delay: .2s;
}

.sidebar.active .logo-menu .toggle-btn {
    left: 90%;
}

.sidebar .link-name {
    opacity: 0;
    pointer-events: none;
    transition: opacity .3s;
}

.sidebar.active .link-name {
    opacity: 1; 
    pointer-events: auto;
    transition-delay: calc(.1s * var(--i));
}

- JS

const sidebar = document.querySelector('.sidebar');
const togglebtn = document.querySelector('.toggle-btn');

togglebtn.addEventListener('click', () => {
    sidebar.classList.toggle('active');
});

