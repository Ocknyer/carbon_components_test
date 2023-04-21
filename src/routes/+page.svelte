<script>
	import 'carbon-components-svelte/css/all.css';
	import {
		Button,
		ImageLoader,
		StructuredList,
		StructuredListHead,
		StructuredListRow,
		StructuredListCell,
		StructuredListBody,
		Tag,
		Tile
	} from 'carbon-components-svelte';

	import poster from '../img/poster.jpg';
</script>

<div id="container">
	<h1 class="title">
		밴드 파수꾼 연합공연 <span>'병목현상'</span>
	</h1>
	<ImageLoader src={poster} style="width: 300px; margin-bottom: 20px" />

	<Tile style="margin-bottom: 20px">
		<div class="about">
			<p class="concertName">'병목현상(甁目現象)'</p>
			<p class="concertDesc">넓은 길이 갑자기 좁아지면서 일어나는 정체 현상</p>
		</div>
		<div class="about-desc">
			<p>이번 공연 ‘병목현상’에서 들려드리는 곡들이 다소 생소할 수 있기에</p>
			<p>여러분께 전해지는 감동의 노폭(路幅)이 좁을 수 있으리라 생각합니다.</p>
			<br class="about-desc-br" />
			<p>그럼에도 불구하고, 언젠가 해소되는 교통체증처럼</p>
			<p>좁은 길을 헤치고 쾌감과 감동을 전해드릴 수 있도록</p>
			<p>진심을 다하고자 하는 공연진의 의지를 담아내었습니다.</p>
		</div>
	</Tile>

	<Button style="margin-bottom: 20px">
		<a href="https://forms.gle/N5xYhdhbJbjy3f4aA" target="_blank" class="reservation"
			>병목현상 예매하기</a
		>
	</Button>

	<StructuredList>
		<StructuredListHead>
			<StructuredListRow head>
				<StructuredListCell head>공연안내</StructuredListCell>
				<StructuredListCell head>정보</StructuredListCell>
			</StructuredListRow>
		</StructuredListHead>
		<StructuredListBody>
			<StructuredListRow>
				<StructuredListCell>일시</StructuredListCell>
				<StructuredListCell>2023년 4월 16일 일요일 18:00 ~ 21:30</StructuredListCell>
			</StructuredListRow>
			<StructuredListRow>
				<StructuredListCell>장소</StructuredListCell>
				<StructuredListCell>001클럽 (서울특별시 마포구 와우산로 18길 20)</StructuredListCell>
			</StructuredListRow>
			<StructuredListRow>
				<StructuredListCell>수용인원</StructuredListCell>
				<StructuredListCell>150명 / 전석 스탠딩</StructuredListCell>
			</StructuredListRow>
			<StructuredListRow>
				<StructuredListCell>티켓</StructuredListCell>
				<StructuredListCell>8,000원</StructuredListCell>
			</StructuredListRow>
		</StructuredListBody>
	</StructuredList>
	<div>
		<Tag type="red">공연</Tag>
		<Tag type="margenta">클럽</Tag>
		<Tag type="cyan">밴드</Tag>
		<Tag type="teal">라이브</Tag>
		<Tag type="green">병목현상</Tag>
	</div>
</div>

<style>
	#container {
		display: flex;
		flex-direction: column;
	}

	.title {
		font-weight: 700;
		margin-bottom: 10px;
	}

	a {
		color: white;
		text-decoration: none;
	}
</style>
