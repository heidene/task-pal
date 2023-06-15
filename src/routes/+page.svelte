<script>
	import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';
	import { InputChip } from '@skeletonlabs/skeleton';

	import Header from '../components/Header.svelte';

	/** @type {Array<string>} */
	let tags = [];
</script>

<Header />
<div class="flex flex-col">
	<form class="flex-grow">
		<div class="px-4 flex gap-4">
			<label class="label pb-4 flex-grow">
				<span>Reminder Title</span>
				<input class="input" type="text" placeholder="Input" />
			</label>
			<button type="button" class="btn-icon btn-icon-sm variant-filled grow-0 self-center -mb-2"
				><svg
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke-width="1.5"
					stroke="currentColor"
					class="w-4 h-4"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						d="M3 3v1.5M3 21v-6m0 0l2.77-.693a9 9 0 016.208.682l.108.054a9 9 0 006.086.71l3.114-.732a48.524 48.524 0 01-.005-10.499l-3.11.732a9 9 0 01-6.085-.711l-.108-.054a9 9 0 00-6.208-.682L3 4.5M3 15V4.5"
					/>
				</svg>
			</button>
		</div>
		<label class="label px-4 pb-4">
			<span>List</span>
			<select class="select">
				<option value="1">Inbox</option>
				<hr />
				<option value="2">Low</option>
				<option value="3">Medium</option>
				<option value="4">High</option>
			</select>
		</label>
		<Accordion>
			<AccordionItem open>
				<!-- <svelte:fragment slot="lead">(icon)</svelte:fragment> -->
				<svelte:fragment slot="summary">Advanced</svelte:fragment>
				<svelte:fragment slot="content">
					<label class="label">
						<span>Description</span>
						<textarea
							class="textarea min-h-fit"
							rows="4"
							placeholder="Lorem ipsum dolor sit amet consectetur adipisicing elit."
						/>
					</label>
					<InputChip class="mt-4" bind:value={tags} name="chips" placeholder="Enter any value..." />
					<label class="label">
						<span>Select</span>
						<select class="select">
							<option value="1">None</option>
							<hr />
							<option value="2">Low</option>
							<option value="3">Medium</option>
							<option value="4">High</option>
						</select>
					</label>
				</svelte:fragment>
			</AccordionItem>
		</Accordion>
	</form>
	<div class="px-4 flex justify-end gap-4 my-4">
		<button type="button" class="btn variant-filled-error">Cancel</button>
		<button type="button" class="btn variant-filled-primary">Create</button>
	</div>
</div>
