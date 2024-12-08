<script lang="ts" setup>
import Card from "@/components/base/Card.vue";
const cardSetting = ref({
    width: '350px',
    height: '450px',
    borderColor: 'gray-10',
    radius: '6px',
    image: 'https://images.unsplash.com/photo-1719937206158-cad5e6775044?q=80&w=2970&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    title: '這是卡片標題',
    titleSize: '24px',
    titleColor: '#000',
    subTitle: 'subTitle',
    subTitleColor: '#78828A',
    subTitleSize: '18px',
    content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident beatae quam dolorem vel repellendus inventore aspernatur deserunt debitis error, doloremque sequi. Porro eos officia hic excepturi cumque numquam est recusandae?',
    contentSize: '16px',
})

</script>


<template>
    <div class="my-4 flex justify-center">
        <p class="text-xl text-green-600 font-bold">
            Hello Nuxt App
        </p>
        <!-- <Card
            class="border border-transparent"
            :width="cardSetting.width"
            :height="cardSetting.height"
            :border-radius="cardSetting.radius"
            :image="cardSetting.image"
            :title="cardSetting.title"
            :title-size="cardSetting.titleSize"
            :sub-title="cardSetting.subTitle"
            :sub-title-color="cardSetting.subTitleColor"
            :sub-title-size="cardSetting.subTitleSize"
            :content="cardSetting.content"
            :content-size="cardSetting.contentSize"
        /> -->
    </div>
</template>