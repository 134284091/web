<!doctype html>
<title>乐器网</title>
<meta name="viewport" content="width=device-width, initial-scale=1" charset = "utf-8">

<script type="text/javascript" src="js/jquery-1.4.1.min.js"></script>
<script type="text/javascript" src="js/jquery.featureCarousel.js"></script>  

<link  rel="stylesheet" href="css/featureCarousel.css"  charset="utf-8"> 



<style type = "text/css">
    *{
        margin: 0px;
        padding:0px;
        
    }
    
    #timeBox{
        color: #ffffff;
    }

    #user{
        color: #ffffff;
        position: absolute;
        right: 3%;
    } a{color: #ffffff; text-decoration: none;}

    #featureCarousel{
        position: absolute;
        background-color: #e7cba8;
        right: 25%;
        height: 0%;
    }

    .menu{
        padding-top: 0px;
        width:1000px;
        height:35px;
    }
    .menu ul{
        list-style: none;
        position: absolute;
        left: 34%;
    }
    .menu ul li{
        position:relative;
        width:120px;
        line-height: 35px;
        text-align:center;
        float:left;
    }
    .menu table{
        position:absolute;
        top:35px;
        left:0;
    }
    .menu ul li a{
        line-height:35px;
        display:block;
        text-align:center;
        color:rgb(255, 255, 255);
        font-size: 20px;
        text-decoration: none;
    }
    .menu ul li a:hover{
        color: rgb(78, 60, 60);
        background: url() no-repeat;
    }
    .menu ul li ul{
        width:120px;
        visibility: hidden;
        position: absolute;
        text-align: left;
        left:0px;
        top: 0px;
        background-color: #ffffff;
    }
    .menu ul li:hover ul{
        visibility: visible;
    }
    .menu ul li ul li ul{
        width:120px;
        visibility: hidden;
        position: absolute;
        text-align: left;
        left:121px;
        top: 0px;
        background-color: #ffffff;
    }
    .menu ul li ul li:hover ul {
        visibility: visible;
    }
    .menu ul li ul li{
        height:35px;
        line-height:35px;
        border-bottom: 1px solid;
        font-size: 14px;
    }
    .menu ul li ul li a{
        display: block;
        color: #666;
    }
    .menu ul li ul li a:hover{
        background:#e7cba8;
    }
    body{
        background-image: url(material/4.jpg);
    }
    .instrument{
        display:flex;
        flex-wrap:wrap;
        padding-top: 350px;
    }
    .row{
        flex-basis:100%;
        display:flex;
        justify-content: center;
    }
    .image{
        margin: 20px;
        height: 150px;
        width: 150px;
    }

    </style>


<body onload="checkCookie()"></body>

<div id="timeBox">
<p>当前时间是:</p>
<p id="time">加载中...</p>
</div>


<div id="user" onload="checkCookie()">
    <a href="#"  id="register" onclick="createCookie()">注册</a><br><p id="userID"></p>
    <a href="#" onclick="deleteCookie()">注销</a>
</div>

<div class = "top">
    <div class = "menu">
        <ul>
            <li><a href = "index.html">首页</a></li>
            <li><a href = "">乐器分类
                <table><tr><td><ul>
                    <li><a href = "">钢琴风琴</a></li>
                    <li><a href = "">交响管弦</a></li>
                    <li><a href = "">民族乐器</a></li>
                    <li><a href = "">打击鼓组</a></li>
                </ul></td></tr></table>
            </a></li>
            <li><a href = "">讨论区</a></li>
            <li><a href = "">乐理</a></li>
            <li><a href = "feedback/feedback.html">反馈</a></li>
        </ul>
    </div>
</div>

<div id="featureCarousel" class="featureCarousel">
    <div class="feature">
        <img alt="Image Caption" src="images/sample1.jpg">
        <div>
            <p>
                钢琴，英文piano，是源自西洋古典音乐中的一种键盘乐器，普遍用于独奏、重奏、伴奏等演出，用于作曲和排练音乐十分方便。弹奏者通过按下键盘上的琴键，牵动钢琴里面包着绒毡的小木槌，继而敲击钢丝弦发出声音。钢琴被称为乐器之王。
            </p>
        </div>
    </div>
    <div class="feature">
        <img alt="Image Caption" src="images/sample2.jpg">
        <div>
            <p>
                小提琴广泛流传于世界各国，是现代管弦乐队弦乐组中最主要的乐器。它在器乐中占非常重要的地位，是现代交响乐队的支柱，也是具有高难度演奏技巧的独奏乐器，与钢琴、古典吉他并称为世界三大乐器。
            </p>
        </div>
    </div>
    <div class="feature">
        <img alt="Image Caption" src="images/sample3.jpg">
        <div>
            <p>
                笛子是迄今为止发现的最古老的汉族乐器 ，也是汉族乐器中最具代表性最有民族特色的吹奏乐器。
            </p>
        </div>
    </div>
   </div>

   <script type="text/javascript">
    $("#featureCarousel").featureCarousel({
    });
</script>      

<script>
    var v = setInterval(function(){timeUpdate()},1000);
    function timeUpdate(){
        var d = new Date();
        var t = d.toLocaleTimeString();
        document.getElementById("time").innerHTML=t;
    }

    function setCookie(cname,cvalue,exdays){
    var d = new Date();
    d.setTime(d.getTime()+(exdays*24*60*60*1000));
    var expires = "expires="+d.toGMTString();
    document.cookie = cname+"="+cvalue+"; "+expires;
}
    function getCookie(cname){
    var name = cname + "=";
    var ca = document.cookie.split(';');
    for(var i=0; i<ca.length; i++) {
        var c = ca[i].trim();
        if (c.indexOf(name)==0) { return c.substring(name.length,c.length); }
    }
    return "";
}

    function checkCookie(){
    var user=getCookie("username");
    if (user!=""){
        alert("欢迎用户 " + user );
        document.getElementById("userID").innerHTML="用户名: " +user;
        document.getElementById("register").remove();
    }
}
    function createCookie(){
        if (user!="" && user!=null){
            user = prompt("请输入你的ID:","");
            setCookie("username",user,30);
            alert("注册成功");
            location.reload(); 
    }
}
    function deleteCookie(){
        if (user!="" && user!=null){
            setCookie("username",user,-30);
            alert("注销成功!");
            location.reload(); 
    }
    }


</script>

<div class = "instrument">
    <div class = "row">
        <a href = "piano/piano.html"><img src="material/instrument/钢琴.png" alt = "加载失败" class = "image"></a>
        <a href = ""><img src="material/instrument/巴松.png" alt = "加载失败" class = "image"></a>
        <a href = ""><img src="material/instrument/二胡.png" alt = "加载失败" class = "image"></a>
    </div>
    <div class = "row">
        <a href = ""><img src="material/instrument/中提琴.png" alt = "加载失败" class = "image"></a>
        <a href = ""><img src="material/instrument/低音提琴.png" alt = "加载失败" class = "image"></a>
        <a href = ""><img src="material/instrument/单簧管.png " alt = "加载失败" class = "image">></a>
    </div>
    <div class = "row">
        <a href = ""><img src="material/instrument/双簧管.png" alt = "加载失败" class = "image"></a>
        <a href=""><img src="material/instrument/古筝.png" alt = "加载失败" class = "image"></a>
        <a href=""><img src="material/instrument/大提琴.png" alt = "加载失败" class = "image"></a>
    </div>
    <div class = "row">
        <a href = ""><img src="material/instrument/小号.png" alt = "加载失败" class = "image"></a>
        <a href=""><img src="material/instrument/小提琴.png" alt = "加载失败" class = "image"></a>
        <a href=""><img src="material/instrument/竖琴.png" alt = "加载失败" class = "image"></a>
    </div>
</div>
