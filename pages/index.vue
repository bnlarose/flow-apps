<template>
  <v-container text-center>
    <v-row>
      <v-col cols="12" fill-height>
        <h1>Home</h1>
        <v-banner single-line>
          <v-avatar
            slot="icon"
            color="secondary"
            size="40"
          >
            <v-icon
              color="white"
            >
              mdi-human-greeting
            </v-icon>
          </v-avatar>

          Welcome back to Flow Apps, [Human] choose an option below

          <!-- <template v-slot:actions>
            <v-btn text color="deep-purple accent-4">Action</v-btn>
            <v-btn text color="deep-purple accent-4">Action</v-btn>
          </template> -->
        </v-banner>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

export default {
}
</script>
