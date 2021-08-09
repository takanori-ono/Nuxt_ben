<template>
    <div>
        <h3>
        ブログ　詳細
        </h3>
        <p>これは、{{ $route.params.id }}のエントリーです。</p>
    </div>
</template>

<script>
export default {
    validate({ params }){
        // 数字だけおっけー
        return /^\d+$/.test(params.id)
    }
}
</script>
