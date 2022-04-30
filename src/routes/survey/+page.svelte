<script>
	import {
		Button,
		Checkbox,
		ComboBox,
		Modal,
		ProgressBar,
		ProgressIndicator,
		ButtonSet,
		ProgressStep,
		RadioButtonGroup,
		RadioButton,
		Slider
	} from 'carbon-components-svelte';

	let open = false;
	let currentIndex = 1;
	let thirdStepCurrent = false;

	const plans = ['Free (1 GB)', 'Standard (10 GB)', 'Pro (128 GB)'];

	let plan = plans[1];

	let max = 328;
	let value = 0;
	let status = 'active';

	$: helperText = value > 0 ? value.toFixed(0) + 'MB of ' + max + 'MB' : 'Press start';
	$: if (value === max) {
		helperText = 'Done';
		status = 'finished';
	}
</script>

<div style="margin-bottom: 20px;"><Checkbox labelText="Label text" /></div>

<div style="margin-bottom: 20px;">
	<ComboBox
		titleText="Contact"
		placeholder="Select contact method"
		items={[
			{ id: '0', text: 'Slack' },
			{ id: '1', text: 'Email' },
			{ id: '2', text: 'Fax' }
		]}
	/>
</div>

<div style="margin-bottom: 20px;">
	<ComboBox
		invalid
		invalidText="Secondary contact method must be different from the primary contact"
		titleText="Contact"
		placeholder="Select contact method"
		items={[
			{ id: '0', text: 'Slack' },
			{ id: '1', text: 'Email' },
			{ id: '2', text: 'Fax' }
		]}
	/>
</div>

<div style="margin-bottom: 30px;">
	<ComboBox
		warn
		warnText="This contact method is not associated with your account"
		titleText="Contact"
		placeholder="Select contact method"
		items={[
			{ id: '0', text: 'Slack' },
			{ id: '1', text: 'Email' },
			{ id: '2', text: 'Fax' }
		]}
	/>
</div>

<div style="margin-bottom: 30px;">
	<Button on:click={() => (open = true)}>Create database</Button>
</div>
<Modal
	bind:open
	modalHeading="Create database"
	primaryButtonText="Confirm"
	secondaryButtonText="Cancel"
	on:click:button--secondary={() => (open = false)}
	on:open
	on:close
	on:submit
>
	<p>Create a new Cloudant database in the US South region.</p>
</Modal>

<div style="margin-bottom: 30px;">
	<ProgressBar value={40} labelText="Upload status" helperText="40 MB of 100 MB" />
</div>

<div style="margin-bottom: 30px;">
	<ProgressBar helperText="Loading..." />
</div>

<div style="margin-bottom: 30px;">
	<ProgressBar
		kind="indented"
		status="finished"
		value={40}
		labelText="Upload file"
		helperText="Upload complete"
	/>
</div>

<div style="margin-bottom: 30px;">
	<ProgressBar labelText="Upload status" {value} {max} {helperText} {status} />

	<ButtonSet style="margin-top: var(--cds-spacing-08)">
		<Button
			disabled={value > 0}
			on:click={() => {
				const interval = setInterval(() => {
					const delta = Math.random() * 10;

					if (value + delta < max) {
						value += delta;
					} else {
						value = max;
						clearInterval(interval);
					}
				}, 30);
			}}
		>
			Start
		</Button>
		<Button
			kind="tertiary"
			disabled={value !== max}
			on:click={() => {
				value = 0;
				status = 'active';
			}}
		>
			Reset
		</Button>
	</ButtonSet>
</div>

<div style="margin-bottom: 20px;">
	<ProgressIndicator bind:currentIndex>
		<ProgressStep
			complete
			label="Step 1"
			description="The progress indicator will listen for clicks on the steps"
		/>
		<ProgressStep
			complete
			label="Step 2"
			description="The progress indicator will listen for clicks on the steps"
		/>
		<ProgressStep
			complete
			bind:current={thirdStepCurrent}
			label="Step 3"
			description="The progress indicator will listen for clicks on the steps"
		/>
		<ProgressStep
			label="Step 4"
			description="The progress indicator will listen for clicks on the steps"
		/>
	</ProgressIndicator>
</div>

<div style="margin-bottom: 30px;">
	<div style="margin: var(--cds-layout-02) 0">
		<Button
			kind={currentIndex === 2 ? 'secondary' : 'primary'}
			on:click={() => {
				currentIndex = currentIndex === 2 ? 0 : 2;
			}}
		>
			Set currentIndex to
			{currentIndex === 2 ? 0 : 2}
		</Button>
	</div>

	<h3>Current index: {currentIndex}</h3>

	<div>Is the third step currently selected? {thirdStepCurrent}</div>
</div>

<div style="margin-bottom: 30px;">
	<RadioButtonGroup legendText="Storage tier (disk)" bind:selected={plan}>
		{#each plans as value}
			<RadioButton labelText={value} {value} />
		{/each}
	</RadioButtonGroup>

	<div style="margin: var(--cds-layout-01) 0">
		{#each plans as value}
			<Button kind="secondary" disabled={plan === value} on:click={() => (plan = value)}>
				Select "{value}"
			</Button>
		{/each}
	</div>

	Selected plan:
	<strong>{plan}</strong>
</div>

<div style="margin-bottom: 30px;">
	<Slider labelText="Instances" value={0} />
</div>
