<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import EmployeeTable from "@/Components/EmployeeTable.vue";
import EmployeeModal from "@/Components/EmployeeModal.vue";
import { Head } from "@inertiajs/vue3";

defineProps({
	employees: {
		type: Array,
	},
});
</script>

<template>
	<Head title="Employee" />

	<AuthenticatedLayout>
		<div class="container py-12">
			<!-- Create User -->
			<div class="flex justify-end">
				<button class="btn-info btn mb-4 py-4" onclick="addEmployeeModal.showModal()">
					Add Employee
				</button>

				<EmployeeModal />
			</div>

			<!-- Employee table -->
			<div class="bg-white sm:rounded-lg">
				<EmployeeTable 
					:employees="employees"
				/>
			</div>
		</div>
	</AuthenticatedLayout>
</template>
