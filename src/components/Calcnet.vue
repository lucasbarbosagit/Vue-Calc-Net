<template>
    <form>
  <div class="form-group">
      <div class="col-xs-2">
    <input type="number" width="48" class="form-control" placeholder="Tamanho do Arquivo" v-model.number="tam"> 
      </div>
  </div>
      <div class="col-xs-2">
   <div class="form-group">
    <select id="byte" class="form-control" v-model="byte">
    <option value="Byte">Byte</option>
    <option value="Kilobyte">Kilobyte</option>
    <option value="Megabyte">Megabyte</option>
    <option value="Gigabyte">Gigabyte</option>
    <option value="Terabyte">Terabyte</option>
    </select>
      </div>
  </div>
   <div class="col-xs-3">
  <div class="form-group">
    <input type="number" class="form-control" placeholder="Velocidade da sua Internet" v-model.number="vel">
  </div>
   </div>
    <div class="col-xs-2">
   <div class="form-group">
    <select id="download" class="form-control" v-model="download">
    <option value="KB">KB</option>
    <option value="MB">MB</option>
    </select>
   </div>
  </div>
  <button class="btn btn-primary calc" @click.prevent="createNew">Calc</button>
  <div>{{ tempfinal }}</div>

</form>

</template>

<script>
export default {
      props: ['tempfinal'],
        data: function() {
            return {
                vel: '',
                tam: '',
                byte: ['Byte','Kilobyte','Megabyte','GigaByte','Terabyte'],
                download: ['KB','MB']
            };
        },
        methods: {
            createNew() {
                this.$emit('velAdded', this.vel, this.tam, this.byte, this.download);
                this.vel = '';
                this.tam = '';
            }
        }
    }

</script>
<style>

.calc {
    margin-bottom: 30px;
}

</style>