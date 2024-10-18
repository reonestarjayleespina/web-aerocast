<template>
    <v-form>
        <v-container>
            <v-row>
                <!-- First Name and Last Name Side by Side -->
                <v-col cols="12" md="6">
                    <v-text-field label="First Name"
                        prepend-icon="mdi-account" required color="teal accent-3"></v-text-field>
                </v-col>

                <v-col cols="12" md="6">
                    <v-text-field label="Last Name" required
                        color="teal accent-3"></v-text-field>
                </v-col>
            </v-row>

            <!-- Email Field on New Line -->
            <v-row>
                <v-col cols="12">
                    <v-text-field label="Email" prepend-icon="mdi-email" type="text"
                        color="teal accent-3"></v-text-field>
                </v-col>
            </v-row>

            <!-- Password Field on New Line -->
            <v-row>
                <v-col cols="12">
                    <v-text-field id="password" label="Password" prepend-icon="mdi-lock"
                        type="password" color="teal accent-3"></v-text-field>
                </v-col>
            </v-row>
        </v-container>
    </v-form>
</template>