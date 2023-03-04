<script setup>
import { ref } from "vue";
import { useForm } from "@inertiajs/vue3";

const showMessage= ref(false);

const form= useForm({
  name: "",
  email: "",
  body: ""
});

// Method
const setShowMessage= (value)=>{
  showMessage.value= value;
}

const cleanForm= ()=>{
  form.reset();
  setShowMessage(true);
  setTimeout(()=> setShowMessage(false), 2500)
}

const submit= ()=>{
  form.post(route('contact'),{
    preserveScroll: true,
    onSuccess: ()=> cleanForm()
  });
};

</script>
<template>
  <section id="contact" class="section bg-light-secondary dark:bg-dark-primary">
    <div
      class="container mx-auto"
    >
      <div class="flex flex-col items-center text-center">
        <h2 class="section-title">Contact Me</h2>
        <p class="subtitle dark:text-light-tail-100">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Fuga veniam
          labore nisium illum cupiditate reiciendis a numquam
        </p>
      </div>
      <div class="flex flex-col lg:flex-row lg:gap-x-8">
        <div
          class="
            flex flex-1 flex-col
            items-start
            space-y-8
            mb-12
            lg:mb-0 lg:pt-2
          "
          v-motion
          :initial="{
            opacity: 0,
            y: 100,
          }"
          :visible="{
            opacity: 1,
            y: 0,
          }"
        >
          <div class="flex flex-col lg:flex-row gap-x-4">
            <div
              class="
                text-accent
                rounded-sm
                w-14
                h-14
                flex
                items-start
                justify-center
                mt-2
                mb-4
                lg:mb-0
                text-2xl
              "
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
                />
              </svg>
            </div>
            <div>
              <h4 class="font-body text-xl mb-1">Have a question?</h4>
              <P class="mb-1 text-paragraph">I am here to help you.</P>
              <p class="text-accent font-normal">Email me at john@doe.com</p>
            </div>
          </div>
          <div class="flex flex-col lg:flex-row gap-x-4">
            <div
              class="
                text-accent
                rounded-sm
                w-14
                h-14
                flex
                items-start
                justify-center
                mt-2
                mb-4
                lg:mb-0
                text-2xl
              "
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"
                />
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"
                />
              </svg>
            </div>
            <div>
              <h4 class="font-body text-xl mb-1">Current Location</h4>
              <P class="mb-1 text-paragraph">Tirana, Albania.</P>
              <p class="text-accent font-normal">Serving clients worldwide.</p>
            </div>
          </div>
          <div class="pt-12">
                        <h5 class="text-lg flex justify-center lg:justify-start items-center text-black dark:text-white mb-2">
                            Follow Me On
                        </h5>
                        <div class="flex items-center">
                            <a
                                class="
                                w-12
                                h-12
                                rounded-full
                                flex
                                items-center
                                justify-center
                                border border-white
                                text-black
                                dark:text-white
                               hover:border-accent
                                dark:hover:bg-dark-secondary dark:hover:border-dark-secondary
                                mr-3
                                sm:mr-4
                                "
                                href="https://facebook.com/laraveller"
                            >
                                <svg
                                width="8"
                                height="16"
                                viewBox="0 0 8 16"
                                class="fill-current"
                                >
                                <path
                                    d="M7.43902 6.4H6.19918H5.75639V5.88387V4.28387V3.76774H6.19918H7.12906C7.3726 3.76774 7.57186 3.56129 7.57186 3.25161V0.516129C7.57186 0.232258 7.39474 0 7.12906 0H5.51285C3.76379 0 2.54609 1.44516 2.54609 3.5871V5.83226V6.34839H2.10329H0.597778C0.287819 6.34839 0 6.63226 0 7.04516V8.90323C0 9.26452 0.243539 9.6 0.597778 9.6H2.05902H2.50181V10.1161V15.3032C2.50181 15.6645 2.74535 16 3.09959 16H5.18075C5.31359 16 5.42429 15.9226 5.51285 15.8194C5.60141 15.7161 5.66783 15.5355 5.66783 15.3806V10.1419V9.62581H6.13276H7.12906C7.41688 9.62581 7.63828 9.41935 7.68256 9.10968V9.08387V9.05806L7.99252 7.27742C8.01466 7.09677 7.99252 6.89032 7.85968 6.68387C7.8154 6.55484 7.61614 6.42581 7.43902 6.4Z"
                                />
                                </svg>
                            </a>
                            <a
                                class="
                                w-12
                                h-12
                                rounded-full
                                flex
                                items-center
                                justify-center
                                border border-white
                                text-black
                                dark:text-white
                                hover:border-accent
                                dark:hover:bg-dark-secondary dark:hover:border-dark-secondary
                                mr-3
                                sm:mr-4
                                "
                                href="https://facebook.com/laraveller"
                            >
                                <svg
                                width="16"
                                height="12"
                                viewBox="0 0 16 12"
                                class="fill-current"
                                >
                                <path
                                    d="M14.2194 2.06654L15.2 0.939335C15.4839 0.634051 15.5613 0.399217 15.5871 0.2818C14.8129 0.704501 14.0903 0.845401 13.6258 0.845401H13.4452L13.3419 0.751468C12.7226 0.258317 11.9484 0 11.1226 0C9.31613 0 7.89677 1.36204 7.89677 2.93542C7.89677 3.02935 7.89677 3.17025 7.92258 3.26419L8 3.73386L7.45806 3.71037C4.15484 3.61644 1.44516 1.03327 1.00645 0.587084C0.283871 1.76125 0.696774 2.88845 1.13548 3.59296L2.0129 4.90802L0.619355 4.20352C0.645161 5.18982 1.05806 5.96477 1.85806 6.52838L2.55484 6.99804L1.85806 7.25636C2.29677 8.45401 3.27742 8.94716 4 9.13503L4.95484 9.36986L4.05161 9.93346C2.60645 10.8728 0.8 10.8024 0 10.7319C1.62581 11.7652 3.56129 12 4.90323 12C5.90968 12 6.65806 11.9061 6.83871 11.8356C14.0645 10.2857 14.4 4.41487 14.4 3.2407V3.07632L14.5548 2.98239C15.4323 2.23092 15.7935 1.8317 16 1.59687C15.9226 1.62035 15.8194 1.66732 15.7161 1.6908L14.2194 2.06654Z"
                                />
                                </svg>
                            </a>
                            <a
                                class="
                                w-12
                                h-12
                                rounded-full
                                flex
                                items-center
                                justify-center
                                border border-white
                                text-black
                                dark:text-white
                                hover:border-accent
                                dark:hover:bg-dark-secondary dark:hover:border-dark-secondary
                                mr-3
                                sm:mr-4
                                "
                                href="https://facebook.com/laraveller"
                            >
                                <svg
                                width="16"
                                height="12"
                                viewBox="0 0 16 12"
                                class="fill-current"
                                >
                                <path
                                    d="M15.6645 1.88018C15.4839 1.13364 14.9419 0.552995 14.2452 0.359447C13.0065 6.59222e-08 8 0 8 0C8 0 2.99355 6.59222e-08 1.75484 0.359447C1.05806 0.552995 0.516129 1.13364 0.335484 1.88018C0 3.23502 0 6 0 6C0 6 0 8.79263 0.335484 10.1198C0.516129 10.8664 1.05806 11.447 1.75484 11.6406C2.99355 12 8 12 8 12C8 12 13.0065 12 14.2452 11.6406C14.9419 11.447 15.4839 10.8664 15.6645 10.1198C16 8.79263 16 6 16 6C16 6 16 3.23502 15.6645 1.88018ZM6.4 8.57143V3.42857L10.5548 6L6.4 8.57143Z"
                                />
                                </svg>
                            </a>
                            <a
                                class="
                                w-12
                                h-12
                                rounded-full
                                flex
                                items-center
                                justify-center
                                border border-white
                                text-black
                                dark:text-white
                                hover:border-accent
                                dark:hover:bg-dark-secondary dark:hover:border-dark-secondary
                                mr-3
                                sm:mr-4
                                "
                                href="https://facebook.com/laraveller"
                            >
                                <svg
                                width="14"
                                height="14"
                                viewBox="0 0 14 14"
                                class="fill-current"
                                >
                                <path
                                    d="M13.0214 0H1.02084C0.453707 0 0 0.451613 0 1.01613V12.9839C0 13.5258 0.453707 14 1.02084 14H12.976C13.5432 14 13.9969 13.5484 13.9969 12.9839V0.993548C14.0422 0.451613 13.5885 0 13.0214 0ZM4.15142 11.9H2.08705V5.23871H4.15142V11.9ZM3.10789 4.3129C2.42733 4.3129 1.90557 3.77097 1.90557 3.11613C1.90557 2.46129 2.45002 1.91935 3.10789 1.91935C3.76577 1.91935 4.31022 2.46129 4.31022 3.11613C4.31022 3.77097 3.81114 4.3129 3.10789 4.3129ZM11.9779 11.9H9.9135V8.67097C9.9135 7.90323 9.89082 6.8871 8.82461 6.8871C7.73571 6.8871 7.57691 7.74516 7.57691 8.60323V11.9H5.51254V5.23871H7.53154V6.16452H7.55423C7.84914 5.62258 8.50701 5.08065 9.52785 5.08065C11.6376 5.08065 12.0232 6.43548 12.0232 8.2871V11.9H11.9779Z"
                                />
                                </svg>
                            </a>
                        </div>
                    </div>
        </div>
        <form @submit.prevent="submit" class="space-y-8 w-full max-w-md">
          <div
            v-if="showMessage"
            class="
              m-2
              p-4
              bg-light-tail-500
              dark:bg-dark-navy-100
              text-light-secondary
              rounded-lg
            "
          >
            Thank you for your message. 
          </div>
          <div class="flex gap-8">
            <div>
              <input
                v-model="form.name"
                type="text"
                class="input dark:text-light-secondary"
                placeholder="Your Name"
              />
              <span v-if="form.errors.name" class="text-sm m-2 text-red-400">{{
                form.errors.name
              }}</span>
            </div>
            <div>
              <input
                v-model="form.email"
                type="email"
                class="input dark:text-light-secondary"
                placeholder="Your Email"
              />
              <span v-if="form.errors.email" class="text-sm m-2 text-red-400">{{
                form.errors.email
              }}</span>
            </div>
          </div>
          <textarea
            v-model="form.body"
            class="textarea dark:text-light-secondary"
            placeholder="Your Meassage"
            spellcheck="false"
          ></textarea>
          <span v-if="form.errors.body" class="text-sm m-2 text-red-400">{{
            form.errors.body
          }}</span>

          <button class="btn btn-lg bg-accent hover:bg-secondary text-white">
            Send message
          </button>
        </form>
      </div>
    </div>
  </section>
</template>