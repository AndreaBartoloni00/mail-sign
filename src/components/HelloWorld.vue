<script setup lang="">

import { ref } from 'vue';
    import { h } from 'vue'
    import { useForm } from 'vee-validate'
    import { toTypedSchema } from '@vee-validate/zod'
    import * as z from 'zod'
import { Button } from '@/components/button'
    import {
    FormControl,
    FormDescription,
    FormField,
    FormItem,
    FormLabel,
    FormMessage,
    } from '@/components/form'
    import { Input } from '@/components/input';
</script>

<template>
  <form @submit="onSubmit">
    <FormField v-slot="{ componentField }" name="username">
      <FormItem>
        <FormLabel>Username</FormLabel>
        <FormControl>
          <Input type="text" placeholder="shadcn" v-bind="componentField" />
        </FormControl>
        <FormDescription>
          This is your public display name.
        </FormDescription>
        <FormMessage />
      </FormItem>
    </FormField>
    <Button type="submit">
      Submit
    </Button>
  </form>
</template>

