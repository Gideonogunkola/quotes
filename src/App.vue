<template>
  <div class="container">
    <Header :quoteCount = "quotes.length" :maxQuotes= "maxQuotes"></Header>
     <Newquote @quoteAdded="newQuote"></Newquote>
     <Quotegrid :quotes = "quotes" @quoteDeleted ="deleteQuote"></Quotegrid>
     <div class="row">
       <div class="col-sm-12 text-center">
         <div class="alert alert-info">Info: Click on Quote to delete it</div>
       </div>
     </div>
  </div>
</template>

<script>
import Quotegrid from '../src/components/Quotegrid'
import Newquote from '../src/components/Newquote'
import Header from '../src/components/Header'
export default {
  name: 'app',
  data () {
    return {
     quotes:['Just a quote to see something'

      ],
      maxQuotes: 10
    }
  },
  methods:{
    newQuote(quote){
      if(this.quotes.length >= this.maxQuotes){
        return alert('Please delete quote first!')
      }
      this.quotes.push(quote)
    },
    deleteQuote(index){
      this.quotes.splice(index, 1)
    }
  },
  components:{
    Quotegrid,
    Newquote,
    Header,
  }
}
</script>

<style>

</style>
