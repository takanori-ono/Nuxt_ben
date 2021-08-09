<template>
    <div style="padding: 30px;">
        <el-button @click="visible=true">開く</el-button>
        <el-dialog :visible.sync="visible" title="確認">
            <p>処理しました。</p>
        </el-dialog>
    </div>
</template>

<script>
export default {
    data: function(){
        return {
            visible: false
        }
    }
}
</script>