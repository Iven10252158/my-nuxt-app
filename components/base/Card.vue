<script lang="ts" setup>
interface ColorMap {
    [index:string]: string
}

interface Props {
    type?: 'default'
    width?: string,
    height?: string,
    borderRadius?: string,
    image?: string,
    title?: string,
    titleColor?: string,
    titleSize?: string,
    subTitle?: string,
    subTitleColor?: string,
    subTitleSize?: string,
    content?: string,
    contentColor?: string,
    contentSize?: string,

    // link?: string,
    // linkColor?: string,
    // linkSize?: string,
    // linkPosition?: string
}

const styleMap = {
    default: 'w-[350px] h-[450px] border border-[#fa0] rounded-lg'
}

const props = withDefaults(defineProps<Props>(), {
  type: 'default'
})

const defaultStyle = computed(() => styleMap[props.type])

// const maxLines = ref(5)
// const contentRef = ref()
// const truncatedContent = ref(props.content);

// const truncateText = () => {
//       const element = contentRef.value;
//       if (!element) return;

//       // 計算行高
//       const lineHeight = parseFloat(getComputedStyle(element).lineHeight);
//       console.log(lineHeight);
      
//       const maxHeight = 120 //lineHeight * maxLines.value;

//       // 動態調整內容，超過高度時進行截斷
//       let text = props.content;
//       element.textContent = text;
//       while (element.scrollHeight > maxHeight && text.length > 0) {
//         console.log(1, text);
        
//         text = text.slice(0, -1);
//         console.log(2, text);
        
//         element.textContent = text + "...";
//       }
//       truncatedContent.value = text + (text.length < props.content.length ? "..." : "");
// };
 // 初始截斷
// onMounted(() => {
//     truncateText();
// });

// watch([() => props.content, maxLines], () => {
//     truncateText();
// });

// const borderColorMap = computed(() => {
//     const colorMap:ColorMap = {
//         'gray-10': 'border-gray-10'
//     }
//     return props.borderColor ? colorMap[props.borderColor] : 'xxx'
// })

</script>

<template>
    <div
        class="card shadow-xl flex flex-col"
        :class="defaultStyle"
        :style="`
        width: ${props.width}; 
        height: ${props.height};
        border-radius: ${props.borderRadius}`"
    >
        <div class="card-header w-full h-1/3" :style="`border-radius: ${props.borderRadius} ${props.borderRadius} 0 0`">
            <img class="w-full h-full object-cover object-center"
            :style="`border-radius: ${props.borderRadius} ${props.borderRadius} 0 0`"
            :src="props.image"
            alt=""
        >
        </div>
        <div class="card-body flex flex-col py-2 px-4 border border-red-500 w-full">
            <h2 class="font-bold border border-indigo-500" :style="`font-size: ${props.titleSize}`">{{ props.title }}</h2>
            <h3 :style="`font-size: ${props.subTitleSize}; color: ${props.subTitleColor}`">{{ props.subTitle }}</h3>
            <p class="border border-amber-400 line-clamp-5" :style="`font-size: ${props.contentSize}`">
                {{ props.content }}
            </p>
        </div>
        <div class="card-footer px-4 flex justify-between items-center grow border border-purple-400">
            <button class="bg-blue-400 px-3 py-2 rounded-md text-white">
                <p class="text-sm">開啟新頁面</p>
            </button>
            <a class="text-xs text-blue-500 underline" href="" >繼續閱讀...</a>
        </div>
    </div>
</template>


<style scoped></style>