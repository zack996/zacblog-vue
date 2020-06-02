<template>
    <el-container>
        <el-aside style="width:10%;margin-top: 50px">
            <switch></switch>
            <SideMenu @indexSelect="listByCategory" ref="sideMenu"></SideMenu>
        </el-aside>
        <el-main style="margin-top: 50px">
            <books ref="booksArea"></books>
        </el-main>
    </el-container>
</template>

<script>
    import SideMenu from "@/components/library/SideMenu";
    import Books from "@/components/library/Book";
    export default {
        name: 'AppLibrary',
        components: {SideMenu,Books},
        methods: {
            listByCategory () {
                var _this = this
                var cid = this.$refs.sideMenu.cid
                var url = 'categories/' + cid + '/books'
                this.$axios.get(url).then(resp => {
                    if (resp && resp.status === 200) {
                        _this.$refs.booksArea.books = resp.data
                    }
                })
            }
        }
    }
</script>

<style scoped>

</style>