<template>
  <layout-wrapper>
   <layout-visual
    title="NUXT SAMPLE SITE DEMO"
    message="お知らせやメニューをmicroCMSを導入したDEMOサイトになります。"
    visual="visual-home"
   />
    <div class="w-full md:max-w-3xl mx-auto pt-20 pb-20 px-6">
      <base-heading>MdN Cafeのおすすめメニュー</base-heading>
      <div class="flex flex-wrap justify-between md:mb-0 mb-10">
        <layout-menu-list 
          v-for="(item, index) in menuItems"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :body="item.body"
          :price="item.price" 
          item-class="md:w-56 md:mb-20 mb-10 shadow-lg bg-gray-200"
          block-class="max-w"
          image-class="w-full"
          data-class="px-6 py-4"
          :flag-body="false"
        />
      </div>
      <base-button name="メニューの一覧" link="/menu/" />
    </div>
    <div class="w-full md:max-w-3xl mx-auto pb-20 px-6">
      <base-heading>MdN Cafeのお知らせ</base-heading>
      <div class="mb-20">
        <layout-information-list
        v-for="(item, index) in infoItems"
        :id="item.id"
        :key="index"
        :date="item.date"
        :title="item.title"
        />
      </div>
      <base-button name="お知らせの一覧" link="/information/" />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
    async asyncData({ $config }) {
    const menu = await axios.get(
      `${$config.apiUrl}/menu?limit=3&filters=flag[equals]true`,
      {
        headers: { 'X-MICROCMS-API-KEY': $config.apiKey },
      }
    )
    const info = await axios.get(`${$config.apiUrl}/information?limit=3`, {
      headers: { 'X-MICROCMS-API-KEY': $config.apiKey },
    })
    return {
      menuItems: menu.data.contents,
      infoItems: info.data.contents,
    }
  },
}
</script>
