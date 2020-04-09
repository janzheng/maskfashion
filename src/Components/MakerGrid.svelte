

<Cytosis 
	tableName={'Mask Makers'} 
	airKey={'keylYLkFHWTY3b8Ca'} 
	airBase={'appU40RlkLFNfoQ3X'} 
  tableQuery={'mask-makers'}
  routeName={'mask-makers'}
  bind:cytosis
  bind:table
>
	<div>
		{#if table}
			<ul class="maker-grid">
				{#each table as item (item.id)}
					{#if item.fields.Photos && item.fields.Photos.length > 0}
						<div class="maker-item-container">
							<div class="maker-item">
								<img alt="{item.fields.Name} thumbnail" src={item.fields.Photos[0].thumbnails.large.url} />
								<div class="maker-desc">
									<div class="maker-name">{item.fields['Name']}</div>
									<div class="maker-location">{item.fields['Location']}</div>
									{#if item.fields['Donation & Pricing Info']}
										<div class="maker-pricing">{@html marked(item.fields['Donation & Pricing Info'])}</div>
									{/if}
								</div>
							</div>
						</div>
					{/if}
				{/each}
			</ul>
		{/if}
	</div>
</Cytosis>





<script>
  import Cytosis from './Components/Cytosis.svelte'
	import marked from 'marked'

	let cytosis, table // bound from pass-through slot

  marked.setOptions({
    gfm: true,
    breaks: true,
  })

</script>




<style type="text/scss">
  .maker-grid {
    list-style: none;

    display: grid;
    gap: 16px;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  	position: relative;

    img {
		  width: 100%;
		  height: 250px;
      object-fit: cover;
    }
  }

  .maker-item-container {
  	border-radius: 6px;

  	.maker-item {
  		// display: flex;
  	}
  }

  .maker-desc {
  	background-color: white;
  	padding: 8px;
  	text-align: left;
  }
</style>



