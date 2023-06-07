<template>
    <div>
        <nav>
            <ul>
                <li><a href="">Home</a></li>
                <li><a href="">About</a></li>
                <li><a href="">Contact</a></li>
            </ul>
        </nav>
    </div>
</template>

<script>

    export default ({

        name: 'Nav_bar',
        
    })
</script>


<style scoped>

    nav {
        background-color: #42b983;
        text-align: center;
    }

    nav ul{
        padding: 0;
    }

    nav li {
        display: inline-block;
        list-style-type: none;
        margin: 0;
        padding: 8px;

    }

    nav ul li a {
        color: #fff;
    }

    nav ul li a:hover {
        background-color: #1b6d85;
    }




</style>