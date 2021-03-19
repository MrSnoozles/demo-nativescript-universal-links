<template>
    <Page>
        <ActionBar>
            <Label text="Home"/>
        </ActionBar>

        <GridLayout>
            <Label class="info">
                <FormattedString>
                    <Span class="fas" text.decode="&#xf135; "/>
                    <Span :text="message"/>
                </FormattedString>
            </Label>
        </GridLayout>
    </Page>
</template>

<script>
  import { Dialogs } from "@nativescript/core";
  import { registerUniversalLinkCallback } from "@nativescript-community/universal-links";

  export default {
    computed: {
      message() {
        return "Blank {N}-Vue app";
      }
    },

    created() {
        registerUniversalLinkCallback((ul) => {
            console.log(ul);
            setTimeout(() => {
                Dialogs.alert("universal link callback executing: " + ul.pathname);
            }, 200);
        });
    }
  };
</script>

<style scoped lang="scss">
    @import '~@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
