<template class = "q-pa-md q-gutter-md">
  <q-card-section>
    Message: {{ msg }}
  </q-card-section>
  <q-separator />
  <q-card-section>
    Using v-html directive: <span v-html = "rawHtml"></span>
  </q-card-section>
  <q-separator />
  <q-card-section>
    <q-btn
      unelevated
      color = "primary"
      type = "a"
      target = "_blank"
      v-bind:id = "linkId"
      v-bind:href = "link.to"
      :title = "link.title"
      :label = "link.label"
    />
  </q-card-section>
  <q-separator />
  <q-card-section>
    <q-btn
      :disable = "isButtonDisabled"
      label = "버튼 보이기" >
    </q-btn>
  </q-card-section>
  <q-separator />
  <q-card-section>
    {{ number + 1 }}
  </q-card-section>
  <q-separator />
  <q-card-section>
    {{ ok ? "YES" : "NO" }}
  </q-card-section>
  <q-separator />
  <q-card-section>
   {{ message.split("").reverse().join("") }}
  </q-card-section>
  <q-separator />
  <q-card-section :id="`list-${id}`">
    list-{{ id }}
  </q-card-section>
  <q-separator />
  <q-card-section class = "text-h6">
    {{ calculateDate() }}
  </q-card-section>
  <q-separator />

  <div class = "q-pa-md row items-start">
    <q-btn
      @click = "increment"
      label = "카운트"
      color = "primary" >
    </q-btn>
    <q-card-section>
      methodCount is: {{ methodCount }}
    </q-card-section>
  </div>
  <q-saparator />

</template>

<script>

export default {
  title:"Vue Basic",
  name:'',
  components:{},
  data(){
    return{
      msg: "hello Vue",
      rawHtml: '<span style = "color: red">빨간색이여야 합니다.</span>',
      linkId: "vue",
	      link: {
	        to: "http://vuejs.org",
	        title: "뷰 공식 사이트",
	        label: "Vuejs.org",
	      },
      isButtonDisabled: true,
			number: 1000,
      ok: true,
	    message: "지금까지 템플릿의 단순한 속성만 있었습니다. 그러나 Vue는 실제로 모든 데이터가 내에서 JavaScript 강화의 모든 기능을 지원합니다.",
	    id: "genie",

      methodCount: 1
    }
  },
  computed:{

  },
  watch:{

  },
  mounted(){
    this.increment()
  },
  methods:{
    calculateDate() {
      /*
      const timeStamp = Date.now();
      const formattedString = Date.formatDate(timeStamp, "YYYY-MM-DD HH:mm");
      return formattedString;
      */
    },

    increment() {
      this.methodCount++;
    }
  }
}
</script>

<style>

</style>
