<script>
  export let story = undefined;
  const { modalBody } = $$props;

  import Layout from '../../internal/ui/Layout.svelte';
  import Button from '../Button';
  import ComposedModal from './ComposedModal.svelte';
  import ModalHeader from './ModalHeader.svelte';
  import ModalBody from './ModalBody.svelte';
  import ModalFooter from './ModalFooter.svelte';

  let open = false;
</script>

<Layout>
  {#if story === undefined}
    <ComposedModal {...$$props.composedModal}>
      <ModalHeader {...$$props.modalHeader} />
      <ModalBody
        {...$$props.modalBody}
        aria-label={modalBody.hasScrollingContent ? 'Modal content' : undefined}>
        <p>Please see ModalWrapper for more examples and demo of the functionality.</p>
        {#if modalBody.hasScrollingContent}
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
        {/if}
      </ModalBody>
      <ModalFooter {...$$props.modalFooter} />
    </ComposedModal>
  {/if}

  {#if story === 'child nodes'}
    <ComposedModal {...$$props.composedModal}>
      <ModalHeader {...$$props.modalHeader}>
        <h1>Testing</h1>
      </ModalHeader>
      <ModalBody
        {...$$props.modalBody}
        aria-label={modalBody.hasScrollingContent ? 'Modal content' : undefined}>
        <p>Please see ModalWrapper for more examples and demo of the functionality.</p>
        {#if modalBody.hasScrollingContent}
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
        {/if}
      </ModalBody>
      <ModalFooter>
        <Button kind="secondary">Cancel</Button>
        <Button kind={$$props.composedModal.danger ? 'danger' : 'primary'}>Primary</Button>
      </ModalFooter>
    </ComposedModal>
  {/if}

  {#if story === 'title'}
    <ComposedModal {...$$props.composedModal} open on:close={() => {}} on:submit={() => {}}>
      <ModalHeader
        {...$$props.modalHeader}
        title="Passive modal title as the message. Should be direct and 3 lines or less." />
      <ModalBody {...$$props.modalBody} />
      <ModalFooter {...$$props.modalFooter} />
    </ComposedModal>
  {/if}

  {#if story === 'trigger'}
    <div>
      <Button
        on:click={() => {
          open = true;
        }}>
        Launch composed modal
      </Button>
    </div>
    <ComposedModal {...$$props.composedModal} {open} on:close={() => (open = false)}>
      <ModalHeader {...$$props.modalHeader} />
      <ModalBody
        {...$$props.modalBody}
        aria-label={modalBody.hasScrollingContent ? 'Modal content' : undefined}>
        <p>Please see ModalWrapper for more examples and demo of the functionality.</p>
        {#if modalBody.hasScrollingContent}
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <h3>Lorem ipsum</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id accumsan augue.
            Phasellus consequat augue vitae tellus tincidunt posuere. Curabitur justo urna,
            consectetur vel elit iaculis, ultrices condimentum risus. Nulla facilisi. Etiam
            venenatis molestie tellus. Quisque consectetur non risus eu rutrum.{' '}
          </p>
        {/if}
      </ModalBody>
      <ModalFooter {...$$props.modalFooter} />
    </ComposedModal>
  {/if}
</Layout>
