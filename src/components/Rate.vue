<template>
<div class="rating">
    <input type="hidden" :name="name" :id="id" v-model="rating_value" />
    <ul class="list">
      <li :key="star" v-for="star in maxstars" :class="{ 'active': star <= rating_value }" class="star" @click="rate(star)">
        <v-icon scale="2" :name="star <= rating_value ? 'star' : 'star-o'"/>
      </li>
    </ul>
  </div>
</template>

<script>

  import 'vue-awesome/icons/star'
  import 'vue-awesome/icons/star-o'
  import Icon from 'vue-awesome/components/Icon'
  
	export default {
        data(){
          return {
              rating_value : this.stars,
          }
        },
        components: {
			'v-icon': Icon
        },
		props : {
            color:{
                type: String,
                default: '#f3d23e'
            },
            hover:{
                type: String,
                default: '#f3d23e'
            },
            id:{
                type: String,
                required: true
            },
            name: {
                type: String,
                required: true,
            },
			stars: {
				type: Number,
				required: true
			},
			maxstars: {
				type: Number,
				default : 5
			}
		},
		methods: {
			rate(star){
				this.rating_value = star
			}
		}
	}
</script>

<style scoped>
	.rating {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		font-size: 14px;
		color: #a7a8a8;
	}

	.list {
		margin: 0 0 5px 0;
		padding: 0;
		list-style-type: none;
	}

	.star {
		display: inline-block;
		cursor: pointer;
	}

	.star:hover ~ .star:not(.active) {
		color: inherit;
	}
    .list:hover .star {
        color: #f3d23e;
    }

	.active {
		color: #f3d23e;
	}
</style>