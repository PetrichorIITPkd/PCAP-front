<div class="container">
    <div class="sidebar">
        <span class="sidebar-text">
             Petrichor / IIT Palakkad // Petrichor / IIT Palakkad // Petrichor / IIT Palakkad // Petrichor / IIT Palakkad // 
        </span>
    </div>
    <div class="main">
        <slot></slot>
    </div>
</div>

<style>
    .sidebar{
        width: 2vw;
        background-color: white;
        color: black;
        writing-mode: sideways-lr;
        -webkit-writing-mode: vertical-lr;
        text-orientation: mixed;
        height: max-content ;
        font-size: 1.5vw;
        bottom: 0;
        display: flex;
        overflow: hidden;
        align-items: center;
        position: fixed;
    }
    .sidebar-text{
        position: relative;
        animation: scrolldown 2s linear infinite;
    }
    @keyframes scrolldown{
        from{
            bottom: 0;
        }
        to{
            bottom: -25.15%;
        }
    }
    @keyframes scrollleft{
        from{
            left: 0;
        }
        to{
            left: -25.15%;
        }
    }
    .container{
        display: flex;
    }
    .main{
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
        height: 100%;
    }
   
    @media (max-width: 1000px){
        
        .sidebar{
            width: max-content;
            height: 5vh;
            background-color: white;
            color: black;
            writing-mode: unset;
            -webkit-writing-mode: unset;
            font-size: 6vw;
            top: 0;
            display: flex;
            overflow: hidden;
            position: fixed;
        }
        .sidebar-text{
            animation: scrollleft 3s linear infinite;
            overflow: unset;
            width: max-content;
            white-space: nowrap;
        }
    }
</style>