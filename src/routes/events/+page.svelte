<script lang="ts">
	import { Card } from 'stwui';

	const cog = 'svg-path';
	const plus_circle = 'svg-path';
	import { Statistic } from 'stwui';
	import { formatNumber } from 'stwui/utils';

	import { Feed } from 'stwui';
	import { formatDate } from 'stwui/utils';

	const check = 'svg-path';
	const currency_usd = 'svg-path';

	interface Item {
		avatar?: string;
		icon?: string;
		content: string;
		date: Date;
	}

	const items: Item[] = [
		{
			icon: '<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M40.1 467.1l-11.2 9c-3.2 2.5-7.1 3.9-11.1 3.9C8 480 0 472 0 462.2V192C0 86 86 0 192 0S384 86 384 192V462.2c0 9.8-8 17.8-17.8 17.8c-4 0-7.9-1.4-11.1-3.9l-11.2-9c-13.4-10.7-32.8-9-44.1 3.9L269.3 506c-3.3 3.8-8.2 6-13.3 6s-9.9-2.2-13.3-6l-26.6-30.5c-12.7-14.6-35.4-14.6-48.2 0L141.3 506c-3.3 3.8-8.2 6-13.3 6s-9.9-2.2-13.3-6L84.2 471c-11.3-12.9-30.7-14.6-44.1-3.9zM160 192a32 32 0 1 0 -64 0 32 32 0 1 0 64 0zm96 32a32 32 0 1 0 0-64 32 32 0 1 0 0 64z"/></svg>',
			content: '<span>Halloween </span>',
			date: new Date(2022, 8, 21, 20, 0)
		},
		{
			icon: currency_usd,
			content:
				'<span>Advanced to phone screeingin by <a href="#item2" class="font-bold">Bethany Blake</a></span>',
			date: new Date(2022, 8, 19)
		},
		{
			icon: check,
			content:
				'<span>Completed phone screening with <a href="#item3" class="font-bold">Martha Gardner</a></span>',
			date: new Date(2022, 8, 15)
		},
		{
			icon: currency_usd,
			content:
				'<span>Advanced to interview by <a href="#item4" class="font-bold">Bethany Blake</a></span>',
			date: new Date(2022, 8, 2)
		},
		{
			icon: check,
			content:
				'<span>Completed interview with <a href="#item5" class="font-bold">Katherine Snyder</a></span>',
			date: new Date(2022, 7, 22)
		}
	];
</script>

<h2>
	If you like to go the same routes at a top speed of 15mph, these rides are <span
		class="text-red-700">not</span
	> for you.
</h2>

<Feed>
	{#each items as item}
		{#if item.avatar}
			<Feed.Item>
				<Feed.Item.Leading slot="leading">
					<Feed.Item.Leading.Avatar slot="avatar" src={item.avatar} />
				</Feed.Item.Leading>
				<Feed.Item.Content slot="content">
					{@html item.content}
				</Feed.Item.Content>
				<Feed.Item.DateTime slot="datetime">
					<time datetime={item.date.toISOString()}>{formatDate(item.date)}</time>
				</Feed.Item.DateTime>
			</Feed.Item>
		{:else if item.icon}
			<Feed.Item>
				<Feed.Item.Leading slot="leading" class="bg-info-background">
					<Feed.Item.Leading.Icon slot="icon" data={item.icon} />
				</Feed.Item.Leading>
				<Feed.Item.Content slot="content">
					{@html item.content}
				</Feed.Item.Content>
				<Feed.Item.DateTime slot="datetime">
					<time datetime={item.date.toISOString()}>{formatDate(item.date)}</time>
				</Feed.Item.DateTime>
			</Feed.Item>
		{:else}
			<Feed.Item>
				<Feed.Item.Content slot="content">
					{@html item.content}
				</Feed.Item.Content>
				<Feed.Item.DateTime slot="datetime">
					<time datetime={item.date.toISOString()}>{formatDate(item.date)}</time>
				</Feed.Item.DateTime>
			</Feed.Item>
		{/if}
	{/each}
</Feed>

Halloween Ride Date TBD Location TBD No Invite Required No Helmet if thats not your thing If you
limit your speed, you limit yourself

<Statistic>
	<Statistic.Title slot="title">Confirmed Attending</Statistic.Title>
	<Statistic.Value class="text-primary" slot="value">
		{formatNumber(10, {
			style: 'decimal',
			notation: 'compact',
			maximumFractionDigits: 0,
			minimumFractionDigits: 0
		})}
	</Statistic.Value>
</Statistic>

<style>
	h2 {
		@apply italic text-zinc-500 text-center animate-pulse;
	}
</style>
