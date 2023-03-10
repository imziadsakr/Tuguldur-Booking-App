<template>
<v-container>
  <v-layout align-center justify-center row wrap>
    <v-flex xs12 sm6 md4>
      <v-dialog
        ref="dialogFromDate"
        v-model="showFromDate"
        :return-value.sync="date1"
        persistent
        lazy
        full-width
        width="290px"
      >
        <v-text-field
          slot="activator"
          v-model="date1"
          label="Check-In Date"
          prepend-icon="event"
          readonly
        ></v-text-field>
        <v-date-picker v-model="date1" scrollable>
          <v-spacer> </v-spacer>
          <v-btn flat color="primary" @click="showFromDate = false">Cancel</v-btn>
          <v-btn flat color="primary" @click="$refs.dialogFromDate.save(date1)">OK</v-btn>
        </v-date-picker>
      </v-dialog>
    </v-flex>

    <v-flex xs12 sm6 md4>
      <v-dialog
        ref="dialogToDate"
        v-model="showToDate"
        :return-value.sync="date2"
        persistent
        lazy
        full-width
        width="290px"
      >
        <v-text-field
          slot="activator"
          v-model="date2"
          label="Check-Out Date"
          prepend-icon="event"
          readonly
        ></v-text-field>
        <v-date-picker v-model="date2" scrollable>
          <v-spacer></v-spacer>
          <v-btn flat color="primary" @click="showToDate = false">Cancel</v-btn>
          <v-btn flat color="primary" @click="$refs.dialogToDate.save(date2)">OK</v-btn>
        </v-date-picker>
      </v-dialog>
    </v-flex>
  </v-layout>
  {{date1}}   {{date2}}

</v-container>
</template>

<script>
  export default {
    data: () => ({
      date1: new Date().toISOString().substr(0, 10),
      date2: new Date().toISOString().substr(0, 10),

      menu: false,
      menu2: false,
      showFromDate : false,
      showToDate : false
    })
  }
</script>

<style>

</style>
