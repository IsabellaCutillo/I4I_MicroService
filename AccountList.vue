<script setup>
import axios from "axios";
import { Field, Form, ErrorMessage } from 'vee-validate';
import * as yup from 'yup';


async function onSubmit(values) {
  const response = await axios.get("https://x1r1mjjffe.execute-api.us-east-1.amazonaws.com/customers/" + values.id);
  console.log(response);
  alert(JSON.stringify(response, null, 2));
}

</script>


<template>
  <Form @submit="onSubmit"> 

    <Field name="id" />
    <ErrorMessage name="id" />

    <button>Get</button>
  </Form>
</template>
