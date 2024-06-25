<script setup lang="">
import { ref } from 'vue';
import { Button } from '/src/components/button';
import {
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from '/src/components/form';
import { Input } from '/src/components/input';

// Definire i dati del form come reactive
const data = ref({
  name: '',
  surname: '',
  rule: '',
  phone: '',
  email: '',
  templateHtml: '',
});
const formSubmitted = ref(false);

// Metodo per gestire il submit del form
const GenerateHtml = () => {
  
  const { name, surname, rule, phone, email} = data.value;
  console.log("Dati del form:", data.value);
  data.value.templateHtml = `
  <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-size:medium;font-family:Arial">
    <tbody>
      <tr>
        <td>
          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
            <tbody>
              <tr>
                <td width="150" style="vertical-align:middle">
                  <span style="margin-right:20px;display:block">
                    <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/File%20Degg%20People/Marco.jpeg" width="130" style="max-width:130px">
                  </span>
                </td>
                <td style="vertical-align:middle">
                  <h3 style="margin:0px;font-size:18px;color:rgb(0,0,0)">${name} ${surname}</h3>
                  <p style="margin:0px;color:rgb(0,0,0);font-size:14px;line-height:22px">${rule}</p>
                  <p style="margin:0px;color:rgb(0,0,0);font-size:14px;line-height:22px">degg srl</p>
                </td>
                <td width="30">
                  <div style="width:30px">&nbsp;</div>
                </td>
                <td width="1" style="width:1px;border-bottom:none;border-left:1px solid rgb(253,205,0)">&nbsp;</td>
                <td width="30">
                  <div style="width:30px">&nbsp;</div>
                </td>
                <td style="vertical-align:middle">
                  <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
                    <tbody>
                      <tr style="vertical-align:middle">
                        <td width="30" style="vertical-align:middle">
                          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
                            <tbody>
                              <tr>
                                <td style="vertical-align:bottom">
                                  <span style="display:block">
                                    <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/phone-call.png" width="13" style="display:block">
                                  </span>
                                </td>
                              </tr>
                            </tbody>
                          </table>
                        </td>
                        <td style="padding:0px;color:rgb(0,0,0)">
                          <a href="tel:+39+0681157585" style="color:rgb(0,0,0);font-size:12px" target="_blank">+39 0681157585</a>&nbsp;|&nbsp;<a href="tel:+39+3456947804" style="color:rgb(0,0,0);font-size:12px" target="_blank">+39 ${phone}</a>
                        </td>
                      </tr>
                      <tr style="vertical-align:middle">
                        <td width="30" style="vertical-align:middle">
                          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
                            <tbody>
                              <tr>
                                <td style="vertical-align:bottom">
                                  <span style="display:block">
                                    <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/email.png" width="13" style="display:block">
                                  </span>
                                </td>
                              </tr>
                            </tbody>
                          </table>
                        </td>
                        <td style="padding:0px">
                          <a href="mailto:${email}" style="color:rgb(0,0,0);font-size:12px" target="_blank">${email}</a>
                        </td>
                      </tr>
                      <tr style="vertical-align:middle">
                        <td width="30" style="vertical-align:middle">
                          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
                            <tbody>
                              <tr>
                                <td style="vertical-align:bottom">
                                  <span style="display:block">
                                    <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/link.png" width="13" style="display:block">
                                  </span>
                                </td>
                              </tr>
                            </tbody>
                          </table>
                        </td>
                        <td style="padding:0px">
                          <a href="https://www.degg.it/" style="color:rgb(0,0,0);font-size:12px" target="_blank">www.degg.it</a>
                        </td>
                      </tr>
                      <tr style="vertical-align:middle">
                        <td width="30" style="vertical-align:middle">
                          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial">
                            <tbody>
                              <tr>
                                <td style="vertical-align:bottom">
                                  <span style="display:block">
                                    <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/location-sign.png" width="13" style="display:block">
                                  </span>
                                </td>
                              </tr>
                            </tbody>
                          </table>
                        </td>
                        <td style="padding:0px">
                          <span style="font-size:12px;color:rgb(0,0,0)">Viale F. Caltagirone 265, 00132, Roma</span>
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </td>
              </tr>
            </tbody>
          </table>
        </td>
      </tr>
      <tr>
        <td>
          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial;width:574.328px">
            <tbody>
              <tr>
                <td height="30">&nbsp;</td>
              </tr>
              <tr>
                <td height="1" style="width:574.328px;border-bottom:1px solid rgb(253,205,0);border-left:none;display:block">&nbsp;</td>
              </tr>
              <tr>
                <td height="30">&nbsp;</td>
              </tr>
            </tbody>
          </table>
        </td>
      </tr>
      <tr>
        <td>
          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial;width:574.328px">
            <tbody>
              <tr>
                <td style="vertical-align:top">
                  <img src="https://degg.it/wp-content/uploads/2021/12/cropped-Logo-degg-2022-svg.png" width="130" style="max-width:130px;display:inline-block">
                </td>
                <td style="text-align:right;vertical-align:top">
                  <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial;display:inline-block">
                    <tbody>
                      <tr>
                        <td>
                          <a href="https://www.facebook.com/degg.digitalevolution" style="display:inline-block;padding:0px" target="_blank">
                            <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/facebook%20(1).png" alt="facebook" height="24" style="max-width:135px;display:block;max-height:24px;display:block">
                          </a>
                        </td>
                        <td width="5">
                          <div>&nbsp;</div>
                        </td>
                        <td>
                          <a href="https://www.linkedin.com/company/degg" style="display:inline-block;padding:0px" target="_blank">
                            <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/linkedin%20(1).png" alt="linkedin" height="24" style="max-width:135px;display:block;max-height:24px;display:block">
                          </a>
                        </td>
                        <td width="5">
                          <div>&nbsp;</div>
                        </td>
                        <td>
                          <a href="https://www.instagram.com/degg_digitalevolution_/" style="display:inline-block;padding:0px" target="_blank">
                            <img src="https://6787801.fs1.hubspotusercontent-na1.net/hubfs/6787801/instagram%20(1).png" alt="instagram" style="max-width:135px;display:block;max-height:24px;display:block">
                          </a>
                        </td>
                        <td width="5">
                          <div>&nbsp;</div>
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </td>
              </tr>
            </tbody>
          </table>
        </td>
      </tr>
      <tr>
        <td>
          <table cellspacing="0" cellpadding="0" style="vertical-align:-webkit-baseline-middle;font-family:Arial;width:574.328px">
            <tbody>
              <tr>
                <td height="15">&nbsp;</td>
              </tr>
            </tbody>
          </table>
        </td>
      </tr>
    </tbody>
  </table>`
  formSubmitted.value = true;
};

// Esportare la funzione per renderla disponibile nel template
defineExpose({
  GenerateHtml
});
</script>

<template>
  <div class="h-[100vh] flex items-center ">
    <div class="w-2/5 mx-auto ">
      <form v-if="!formSubmitted" @submit.prevent="GenerateHtml" class="w-full">
        <FormField v-slot="{ componentField }" name="name">
          <FormItem>
            <FormControl>
              <Input type="text" name="name" placeholder="name" v-model="data.name" v-bind="componentField" class="border-none mb-2 shadow-[0_0px_5px_0px_rgba(0,0,0,0.2)] rounded-[10px]"/>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>

        <FormField v-slot="{ componentField }" name="surname">
          <FormItem>
            <FormControl>
              <Input type="text" name="surname" placeholder="surname" v-model="data.surname" v-bind="componentField" class="border-none mb-2 shadow-[0_0px_5px_0px_rgba(0,0,0,0.2)] rounded-[10px]"/>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>
        
        <FormField v-slot="{ componentField }" name="rule">
          <FormItem>
            <FormControl>
              <Input type="text" name="rule" placeholder="rule" v-model="data.rule" v-bind="componentField" class="border-none mb-2 shadow-[0_0px_5px_0px_rgba(0,0,0,0.2)] rounded-[10px]"/>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>

        <FormField v-slot="{ componentField }" name="phone">
          <FormItem>
            <FormControl>
              <Input type="text" name="phone" placeholder="phone" v-model="data.phone" v-bind="componentField" class="border-none mb-2 shadow-[0_0px_5px_0px_rgba(0,0,0,0.2)] rounded-[10px]"/>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>

        <FormField v-slot="{ componentField }" name="email">
          <FormItem>
            <FormControl>
              <Input type="email" name="email" placeholder="email" v-model="data.email" v-bind="componentField" class="border-none mb-2 shadow-[0_0px_5px_0px_rgba(0,0,0,0.2)] rounded-[10px]"/>
            </FormControl>
            <FormMessage />
          </FormItem>
        </FormField>
        <Button type="submit" class="bg-black rounded-[10px] text-white mt-2 hover:bg-black">
          Submit
        </Button>
      </form>
      <div v-if="formSubmitted" v-html="data.templateHtml" class="mt-10"></div>
    </div>
    
  </div>



  <!-- <div id="template"></div> -->
  
</template>



