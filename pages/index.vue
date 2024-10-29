
<template>
<div class="flex items-stretch h-screen">
    <div class="p-6 flex items-center justify-center \ flex-1">
        <form class="flex flex-col gap-6 w-full sm:w-auto">
            <h1 class="text-3xl">
                <!-- <span class="pi pi-user"> </span> -->
                <span>Registration</span>
            </h1>

            <div class="flex flex-col sm:flex-row sm:items-center gap-6">
                <div class="flex-auto">
                    <label for="firstname" class="block font-semibold mb-2">Firstname</label>
                    <InputText id="firstname" class="w-full" />
                </div>
                <div class="flex-auto">
                    <label for="lastname" class="block font-semibold mb-2">Lastname</label>
                    <InputText id="lastname" class="w-full" />
                </div>
            </div>
            <div class="flex flex-col sm:flex-row sm:items-center gap-6">
                <div class="flex-1">
                    <label for="date" class="block font-semibold mb-2">Date</label>
                    <DatePicker inputId="date" class="w-full" />
                </div>
                <div class="flex-1">
                    <label for="country" class="block font-semibold mb-2">Country</label>
                    <Select v-model="selectedCountry" inputId="country" :options="countries" optionLabel="name" placeholder="Select a Country" class="w-full">
                        <template #value="slotProps">
                            <div v-if="slotProps.value" class="flex items-center">
                                <img :alt="slotProps.value.label" src="https://primefaces.org/cdn/primevue/images/flag/flag_placeholder.png" :class="`mr-2 flag flag-${slotProps.value.code.toLowerCase()}`" style="width: 18px" />
                                <div>{{ slotProps.value.name }}</div>
                            </div>
                            <span v-else>
                                {{ slotProps.placeholder }}
                            </span>
                        </template>
                        <template #option="slotProps">
                            <div class="flex items-center">
                                <img :alt="slotProps.option.label" src="https://primefaces.org/cdn/primevue/images/flag/flag_placeholder.png" :class="`mr-2 flag flag-${slotProps.option.code.toLowerCase()}`" style="width: 18px" />
                                <div>{{ slotProps.option.name }}</div>
                            </div>
                        </template>
                    </Select>
                </div>
            </div>
            <div class="flex-auto">
                <label for="message" class="block font-semibold mb-2">Message</label>
                <Textarea id="message" class="w-full" rows="4" />
            </div>
            
            <Button icon="pi pi-check" label="submit" />
        </form>
    </div>
    <div class="flex flex-1 items-center justify-center">
        <svg width="35" height="40" viewBox="0 0 35 40" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="..." fill="var(--p-text-color)"/>
            <path d="..." fill="transparent" />
        </svg>
    </div>
</div>
</template>

<script setup>
</script>
