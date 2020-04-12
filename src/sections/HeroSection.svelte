
<div class="Hero-section">
	<div class="image-tagline">
		<img
			src="images/hero.jpg"
			alt="Illustrated group of people wearing face masks"
		/>

		<div class="hero-tagline">
			<h2>“My mask protects you, your mask protects me.”</h2>
			<h3>#maskfashion: discover mask makers</h3>
		</div>
	</div>
	<div class="explainer">
		{@html marked(explainer)}
		<!-- At Mask Fashion, we are trying to normalize mask wearing in order to create a safer place for everyone. With the Coronavirus pandemic, the CDC recommends everyone wear a mask in order to mitigate the risk for spreading the virus. So, let's get creative with our masks! Let's encourage displaying and wearing awesome, great-looking masks in public. I used to feel weird wearing my mask outside, but now with more people doing it, I feel better about wearing mine in public. -->
	</div>
</div>



<script>
  import { content } from '../stores.js';
	import _cytosis from 'cytosis'
	import marked from 'marked'

  marked.setOptions({
    gfm: true,
    breaks: true,
  })

	$: console.log('content?', $content)
	// let body = 'text'

	let explainer = ''
  $: if($content) {
  	explainer = _cytosis.findField('explainer', $content, 'Markdown' )
  }

</script>

<style type="text/scss">
	@import './styles/core';

	.Hero-section {
		.image-tagline {
			margin-left: -32px;
			margin-right: -32px;
			position: relative;
			height: 368px;

			img {
				width: 100%;
				height: 100%;
				object-fit: cover;
			}

			.hero-tagline {
				position: absolute;
				top: 115px;
				left: 30px;
				width: 225px;
				background: white;
				border-radius: 10px;
				padding: 14px 12px 26px 12px;
				font-weight: 300;

				h2, h3 {
					font-weight: 400;
				}

				h2 {
					font-size: 30px;
					line-height: 35px;
					padding-bottom: 12px;
				}

				h3 {
					font-size: 16px;
					line-height: 19px;
					padding-bottom: 0;
				}
			}
		}

		.explainer {
			padding: 20px 0;
		}
	}

	@media (min-width: 768px) {
		.Hero-section {
			.image-tagline {
				height: 500px;

				.hero-tagline {
					width: 413px;
					padding: 45px 48px;
					top: 80px;
    				left: 45px;
					
					h2 {
						font-size: 38px;
    					line-height: 47px;
					}

					h3 {
						font-size: 28px;
    					line-height: 35px;
					}
				}
			}
		}
	}
</style>


