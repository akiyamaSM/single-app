<template>
<div class="rating">
    <ul class="list">
      <li :key="star" v-for="star in maxStars_" :class="{ 'active': star <= stars_ }" class="star" @click="rate(star)">{{ star }}</li>
    </ul>
    <span>{{ stars_ }} of {{ maxStars_ }}</span>
  </div>
</template>

<script>
	export default {
		mounted(){
			console.log(this.stars)
		},
		props : {
			stars: {
				type: Number,
				required: true
			},
			maxstars: {
				type: Number,
				default : 5
			}
		},
		data(){
			return {
				stars_ : this.stars,
				maxStars_ : this.maxstars
			}
		},
		methods: {
			rate(star){
				this.stars_ = star;
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

	.list:hover .star {
		color: #f3d23e;
	}

	.star {
		display: inline-block;
		cursor: pointer;
	}

	.star:hover ~ .star:not(.active) {
		color: inherit;
	}

	.active {
		color: #f3d23e;
	}

</style>