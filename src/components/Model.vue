<template>
    <button class="btn btn-danger" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasWithBothOptions"
        aria-controls="offcanvasWithBothOptions">OffCanvas</button>

    <div class="offcanvas offcanvas-start" data-bs-scroll="true" tabindex="-1" id="offcanvasWithBothOptions"
        aria-labelledby="offcanvasWithBothOptionsLabel">
        <div class="offcanvas-header">
            <h5 :class="{ highlight: headerHighlight }" class="offcanvas-title" id="offcanvasWithBothOptionsLabel">{{
                title }}</h5>
            <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
        </div>
        <div class="offcanvas-body">
            <p>{{ description }}</p>
        </div>
    </div>
</template>

<script scoped>
export default {
    props: ['title', 'description', 'headerHighlight']
}
</script>


<style>
.highlight {
    color: red;
    font-weight: bold;
}
</style>
