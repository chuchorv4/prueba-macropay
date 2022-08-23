<template>
  <b-container class="main">
    <b-card-group columns>
      <b-card v-for="item in items" :key="item._id" no-body>
        <b-card-img :src="item.image" alt="Card image" v-on:click="showModalDetail(item)" :top="true"></b-card-img>
        <b-card-text class="p-2">
          <h5>
            {{ item.brand }} - {{ item.model }}
          </h5>
          <p class="item-price">
            {{ item.price | toCurrency }}
          </p>
          <b-form inline>
            <b-form-input v-model="item.count" id="count" type="number" class="input-add-cart"></b-form-input>
            <b-button variant="primary">Add</b-button>
          </b-form>
        </b-card-text>
      </b-card>
    </b-card-group>
  
  <b-modal id="modal-detail" :title="`${ itemSelected.brand } - ${ itemSelected.model }`">
    <Carrousel :images="itemSelected.images" />
    <p>
      {{ itemSelected.description }}
    </p>
    <p class="item-price">
      {{ itemSelected.price | toCurrency }}
    </p>
  </b-modal>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      itemSelected: {}
    }
  },
  async asyncData({ $axios }) { // Fetch data from Server API
    // call to API
    return { // data dump for test
      items: [
        {
          image: 'https://via.placeholder.com/180',
          images: [
            'https://via.placeholder.com/600x400?text=Image+1',
            'https://via.placeholder.com/600x400?text=Image+2'
          ],
          brand: 'Nokia',
          model: '1100',
          price: 1234.12,
          count: 1,
          description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Velit reprehenderit voluptate perspiciatis sunt error incidunt adipisci quod recusandae vero doloribus molestiae repellat ab dolore nisi fuga, ut minima temporibus tempora.'
        },
        {
          image: 'https://via.placeholder.com/180',
          images: [
            'https://via.placeholder.com/600x400?text=Image+1',
            'https://via.placeholder.com/600x400?text=Image+2'
          ],
          brand: 'Motorola',
          model: 'L21',
          price: 526.12,
          count: 1,
          description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Velit reprehenderit voluptate perspiciatis sunt error incidunt adipisci quod recusandae vero doloribus molestiae repellat ab dolore nisi fuga, ut minima temporibus tempora.'
        },
        {
          image: 'https://via.placeholder.com/180',
          images: [
            'https://via.placeholder.com/600x400?text=Image+1',
            'https://via.placeholder.com/600x400?text=Image+2',
            'https://via.placeholder.com/600x400?text=Image+3'
          ],
          brand: 'Xiaomi',
          model: 'P01',
          price: 826.00,
          count: 1,
          description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Velit reprehenderit voluptate perspiciatis sunt error incidunt adipisci quod recusandae vero doloribus molestiae repellat ab dolore nisi fuga, ut minima temporibus tempora.'
        },
        {
          image: 'https://via.placeholder.com/180',
          images: [
            'https://via.placeholder.com/600x400?text=Image+1',
            'https://via.placeholder.com/600x400?text=Image+2'
          ],
          brand: 'Huawei',
          model: 'X',
          price: 5786.30,
          count: 1,
          description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Velit reprehenderit voluptate perspiciatis sunt error incidunt adipisci quod recusandae vero doloribus molestiae repellat ab dolore nisi fuga, ut minima temporibus tempora.'
        },
        {
          image: 'https://via.placeholder.com/180',
          images: [
            'https://via.placeholder.com/600x400?text=Image+1',
            'https://via.placeholder.com/600x400?text=Image+2'
          ],
          brand: 'Siemens',
          model: 'C35',
          price: 786.30,
          count: 1,
          description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Velit reprehenderit voluptate perspiciatis sunt error incidunt adipisci quod recusandae vero doloribus molestiae repellat ab dolore nisi fuga, ut minima temporibus tempora.'
        }
      ]
    }
  },
  filters: {
    toCurrency: function (value) {
      return Intl.NumberFormat("es-MX", {
        style: "currency",
        currency: "MXN",
      }).format(value);
    }
  },
  methods: {
    showModalDetail(value) {
      this.itemSelected = value;
      this.$root.$emit('bv::show::modal', 'modal-detail');
    },
  }
}
</script>
<style scoped>
.main {
  min-height: 800px;
  margin: 10px;
}
.item-price {
  font-size: 30px;
  text-align: right;
}
.input-add-cart {
  width: 45%;
  margin-right: 10px;
}
</style>