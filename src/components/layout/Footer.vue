<script setup></script>
<template>
    <footer>
        <div class="center-wr">
            <div class="footer">
                <div class="col-4">
                    coloumn one
                </div>
                <div class="col-4">
                    coloumn two
                </div>
                <div class="col-4">
                    column Three
                </div>
            </div>
        </div>
    </footer>
</template>
<style>
.page-content {
    margin: 20px 0px;
}

footer {
    background-color: black;
    padding: 20px;
}

.footer {
    display: flex;
    justify-content: space-between;
}

.col-4 {
    width: 33%;
    margin: 15px;
    color: #fff;
}
</style>