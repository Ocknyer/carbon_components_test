<script>
	import {
		PaginationNav,
		DataTable,
		Tabs,
		Tab,
		TabContent,
		Tile,
		Pagination,
		Search
	} from 'carbon-components-svelte';
</script>

<Search placeholder="Search catalog..." value="Cloud functions" />

<Tile>
	<section class="lineup-section">
		<!-- <h1>lineup</h1>
		<p>PSAT (Pure Sound Audio Team)</p>
		<p>백색왜성</p>
		<p>밴드 파수꾼</p> -->
	</section>
</Tile>

<Tabs>
	<Tab label="PSAT" />
	<Tab label="백색왜성" />
	<Tab label="파수꾼" />
	<svelte:fragment slot="content">
		<TabContent
			><DataTable
				headers={[
					{ key: 'number', value: '순서' },
					{ key: 'singer', value: '가수' },
					{ key: 'song', value: '곡명' }
				]}
				rows={[
					{
						id: 1,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 2,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 3,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 4,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 5,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					}
				]}
			>
				<strong slot="title">PSAT</strong>
				<span slot="description" style="font-size: 1rem">홍길동, 엄복동, 뉴진스, 쿠키</span>
			</DataTable></TabContent
		>
		<TabContent
			><DataTable
				headers={[
					{ key: 'number', value: '순서' },
					{ key: 'singer', value: '가수' },
					{ key: 'song', value: '곡명' }
				]}
				rows={[
					{
						id: 1,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 2,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 3,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 4,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 5,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					}
				]}
			>
				<strong slot="title">백색왜성</strong>
				<span slot="description" style="font-size: 1rem">홍길동, 엄복동, 뉴진스, 쿠키</span>
			</DataTable></TabContent
		>
		<TabContent
			><DataTable
				headers={[
					{ key: 'number', value: '순서' },
					{ key: 'singer', value: '가수' },
					{ key: 'song', value: '곡명' }
				]}
				rows={[
					{
						id: 1,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 2,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 3,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 4,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					},
					{
						id: 5,
						number: '1',
						singer: '유다빈밴드',
						song: 'Letter'
					}
				]}
			>
				<strong slot="title">파수꾼</strong>
				<span slot="description" style="font-size: 1rem">홍길동, 엄복동, 뉴진스, 쿠키</span>
			</DataTable></TabContent
		>
	</svelte:fragment>
</Tabs>

<PaginationNav />
<Pagination totalItems={102} pageSizes={[10, 15, 20]} />
