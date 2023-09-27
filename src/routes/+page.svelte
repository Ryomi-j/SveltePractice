<script>
	import { v4 as uuid } from 'uuid';

	import Header from '../components/Header.svelte';
	import List from '../components/List.svelte';
	import Info from '../components/Info.svelte';

	// Todo : checkbox 연결
	// Todo : Item 추가
	// Todo : Item update
	// Todo : Item delete
	// Todo : Edit Mode
	// Todo : CSS Effect - fade, flip
	
	let todos = [
		{
			id: uuid(),
			content: '첫 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '두 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '세 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '네 번째 할 일',
			done: false
		}
	];

</script>

<Header />
<Info />
<List />
