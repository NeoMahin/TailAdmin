<script setup>

import Count from '../../components/Count/Count.vue'
import ServiceCardData from '../../components/Card/ServiceCardData.vue'
import InformationCardData from '../../components/Card/InformationCardData.vue'
import Contact from '../../components/Forms/Contact/Contact.vue'
import ClientSec from '../../components/Client/ClientSec.vue'
import FooterSec from '../../components/Footer/FooterSec.vue'
import PricePlan from '../../components/PricePlan/PricePlan.vue'
import RecommendationsData from '../../components/Recommendations/RecommendationsData.vue'
import BlogSec from '../../components/Blog/BlogSec.vue'
import NewsLetterData from '../../components/NewsLetter/NewsLetterData.vue'
import ExperienceSec from '../Experience/ExperienceSec.vue'

</script>
  
<template>

    <count />
  
    <div class="px-4 lg:px-7">
  
        <service-card-data />
        <price-plan />
        <recommendations-data />
        <BlogSec/>
        <experience-sec />
        <news-letter-data />
        <information-card-data />
        <Contact />
        <client-sec />
        <footer-sec />
    </div>
  
  </template>
  
