<template>
    <div>
        <md-menu md-size="medium" md-align-trigger class="dropdown">
            <md-button md-menu-trigger>Ribbons</md-button>
            <md-menu-content>
                <md-menu-item @click="showDialog = true">Cart</md-menu-item>
                <md-menu-item @click="settingDialog = true">Personal Settings</md-menu-item>
            </md-menu-content>
        </md-menu>
    
        <md-dialog :md-active.sync="showDialog">
            <md-dialog-title>Cart</md-dialog-title>
            
            <md-tabs md-dynamic-height>
                <md-tab md-label="Tab1">
                    <Tab1 />
                </md-tab>

                <md-tab md-label="Tab2">
                    <Tab2 />
                </md-tab>

                <md-tab md-label="Tab3">
                    <Tab3 />
                </md-tab>
            </md-tabs>

            <md-dialog-actions>
                <md-button class="md-primary" @click="showDialog = false">Close</md-button>
                <md-button class="md-primary" @click="showDialog = false">Save</md-button>
            </md-dialog-actions>
        </md-dialog>

        <md-dialog :md-active.sync="settingDialog">
            <md-dialog-title>Personal Settings</md-dialog-title>
            
            <md-content class="md-content-body" md-dynamic-height>
                <personal-settings />
            </md-content>

            <md-dialog-actions>
                <md-button class="md-primary" @click="settingDialog = false">Close</md-button>
                <md-button class="md-primary" @click="settingDialog = false">Save</md-button>
            </md-dialog-actions>
        </md-dialog>
    </div>
</template>

<script>
    import Tab1 from '~/components/tabs/Tab1.vue'
    import Tab2 from '~/components/tabs/Tab2.vue'
    import Tab3 from '~/components/tabs/Tab3.vue'
    import PersonalSettings from '~/components/PersonalSettings.vue'

    export default {
        components: {
            Tab1,
            Tab2,
            Tab3,
            PersonalSettings
        },
        data: ()=>({
            showDialog: false,
            settingDialog: false
        })
    }    
</script>
