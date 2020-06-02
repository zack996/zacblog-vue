<template>
    <el-container>
        <el-aside style="width:10%;margin-top: 50px">
            <switch></switch>
            <SideMenu></SideMenu>
        </el-aside>
        <el-main style="margin-top: 50px">
            <books></books>
        </el-main>
    </el-container>
</template>

<script>
    import SideMenu from "@/components/library/SideMenu";
    import Books from "@/components/library/Book";
    export default {
        name: 'AppLibrary',
        components: {SideMenu,Books}
    }
</script>

<style scoped>

</style>