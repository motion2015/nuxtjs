<template>
<section class="recipes">
    <Recipe
        v-for="recipe in recipes"
        :key="recipe.id"
        :thumbnail="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText" />
    <!-- <article class="recipe">
    <div class="thumbnail" style="background-image: url('https://www.goodfood.com.au/content/dam/images/h/0/f/a/q/i/image.related.wideLandscape.940x529.h0fa4n.png/1515456591895.jpg')"></div>
    <h1>Title</h1>
    <p>Some nice previe text</p>
    </article>
    <article class="recipe">
    <div class="thumbnail" style="background-image: url('https://edge.alluremedia.com.au/m/l/2017/08/PizzaSlice.jpg')"></div>
    <h1>Title</h1>
    <p>Some nice previe text</p>
    </article> -->
</section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
    components: {
        Recipe
    },
    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Deliciout Pizza",
                            previewText: "Awesome Pizza!",
                            thumbnail: "https://www.goodfood.com.au/content/dam/images/h/0/f/a/q/i/image.related.wideLandscape.940x529.h0fa4n.png/1515456591895.jpg"
                        },
                        {
                            id: "2",
                            title: "Deliciout Food",
                            previewText: "Very tasty indeed!",
                            thumbnail: "https://edge.alluremedia.com.au/m/l/2017/08/PizzaSlice.jpg"
                        }
                    ]
                })
            }, 1500);
        })
    }
}
</script>

<style>
.recipes {
    display:flex;
    flex-flow: row wrap;
    justify-content:center;
    align-items:center;
}
.recipe {
    box-sizing: border-box;
    width:280px;
    padding:8px;
    border:1px solid #ccc;
    box-shadow: 0 2px 2px #aaa;
    margin:10px;
}
.thumbnail {
    background-position: center;
    background-size: cover;
    width:100%;
    height:200px;
}
</style>