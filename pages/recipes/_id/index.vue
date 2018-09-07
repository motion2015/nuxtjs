<template>
    <!-- <p>{{ $route.params.id }}</p> -->
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p>{{recipe.descriptionText}}}</p>
    </section>
</template>
<script>
export default {
    asyncData(context) {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: "Deliciout Pizza",
                            previewText: "Awesome Pizza!",
                            descriptionText: "This is really a delicius Pizza!",
                            thumbnail: "https://www.goodfood.com.au/content/dam/images/h/0/f/a/q/i/image.related.wideLandscape.940x529.h0fa4n.png/1515456591895.jpg"
                        },
                        {
                            id: "2",
                            title: "Deliciout Food",
                            previewText: "Very tasty indeed!",
                            descriptionText: "This is really a tasty indeed!",
                            thumbnail: "https://edge.alluremedia.com.au/m/l/2017/08/PizzaSlice.jpg"
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500);
        })
    }
}
</script>
<style scoped>
.single-recipe {
    display:flex;
    flex-flow:column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding:30px;
}
.recipe-image {
    width:100%;
}
</style>