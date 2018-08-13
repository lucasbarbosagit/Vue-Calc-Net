<template>
  <div id="app">
   <app-header></app-header>
   <app-calcnet :tempfinal="tempfinal" @velAdded="newTemp" :bytes="byte"></app-calcnet>
  </div>
</template>

<script>
 import Header from './components/Header.vue';
 import Calcnet from './components/Calcnet.vue';

export default {
        data: function () {
            return {
              tempfinal: '',
            }
        },
        methods: {
          newTemp(vel, tam, byte, download) {
                if (vel == '') {
                    return alert('Digite um valor');
                }
                else if (byte == 'Byte' && download == 'KB') {
                    return this.tempfinal = 'Seu Download demorará ' + ((tam / 1000) / (vel / 8)) + ' segundos.' ;
                  }// certo
                else if (byte == 'Kilobyte' && download == 'KB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam) / (vel / 8)) + ' segundos.' ;
                  } // certo
                else if (byte == 'Megabyte' && download == 'KB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000) / (vel / 8)) + ' segundos.' ;
                  }// certo
                else if (byte == 'Gigabyte' && download == 'KB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000 * 1000) / (vel / 8)) + ' segundos.' ;
                  }// certo
                else if (byte == 'Terabyte' && download == 'KB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000 * 1000 * 1000) / (vel / 8)) + ' segundos.' ;
                  }// início do MB -- certo
                else if (byte == 'Byte' && download == 'MB') {
                    return this.tempfinal = 'Seu Download demorará ' + ((tam / 1000) / (vel * 1024 / 8)) + ' segundos.' ;
                  }// certo
                else if (byte == 'Kilobyte' && download == 'MB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam) / (vel * 1024 / 8)) + ' segundos.' ;
                  } // certo
                else if (byte == 'Megabyte' && download == 'MB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000) / (vel * 1024 / 8)) + ' segundos.' ;
                  } // certo
                else if (byte == 'Gigabyte' && download == 'MB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000 * 1000) / (vel * 1024 / 8)) + ' segundos.' ;
                  } // certo
                else if (byte == 'Terabyte' && download == 'MB'){
                    return this.tempfinal = 'Seu Download demorará ' + ((tam * 1000 * 1000 * 1000) / (vel * 1024 / 8)) + ' segundos.' ;
                  }  // certo
           },
         transtime(){
           
         }  
        },
        components: {
            appHeader: Header,
            appCalcnet: Calcnet
        }
    }

</script>
<style>
</style>