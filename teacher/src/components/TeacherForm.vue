<template>

    <section>
        <h3>Añadir Profesor</h3>
        <div><label>Nombre:</label> <input type="text" v-model="teacher.teacherName"></div>
        <div><label>Apellidos:</label> <input type="text" v-model="teacher.surname"></div>
        <div><label>DNI / NIF:</label> <input type="text" v-model="teacher.dni"></div>
        <div><label>Materias:</label> <input type="text" v-model="subject"> <button @click="handleSubject()">Agregar</button></div>
        <div>
            <ul>
                <li v-for="(subj, index) in teacher.subjects" :key="index">{{ subj }}</li>
            </ul>
        </div>
        <input type="checkbox" v-model="teacher.doc"> Documentación Entregada
        <button @click="handleAddTeacher()">Agegar</button>
    </section>

    <section>
        <h3>Listado de profesores</h3>
        <table>
            <tr>
                <th>Nombre</th>
                <th>Apellidos</th>
                <th>DNI / NIF</th>
                <th>Materias</th>
                <th>Documentación Entregada</th>
            </tr>
            <tr v-for="teacher in teachers" :key="teacher.dni">
                <td>{{ teacher.teacherName }}</td>
                <td>{{ teacher.surname }}</td>
                <td>{{ teacher.dni }}</td>
                <td>
                    <ul>
                        <li v-for="(subje, index) in teacher.subjects" :key="index"> {{ subje }}</li>
                    </ul>
                </td>
                <td v-if="teacher.doc">Entregada</td>
                <td v-else>No entregada</td>
            </tr>
        </table>
    </section>
</template>

<script lang="ts" setup>

    import {Ref, ref} from 'vue'

    interface ITeacher {
        teacherName: string,
        surname: string,
        dni: string,
        subjects: Array<string>,
        doc: boolean
    }

    let teacher:Ref<ITeacher> = ref({
        teacherName: '',
        surname: '',
        dni: '',
        subjects: [],
        doc: false
    })

    let teachers:Ref<Array<ITeacher>> = ref([])

    let subject:Ref<string> = ref('')

    const handleSubject = () => {
        teacher.value.subjects.push(subject.value)
        subject.value = ""
    }

    const handleAddTeacher = () => {
        teachers.value.push({
            teacherName: teacher.value.teacherName,
            surname: teacher.value.surname,
            dni: teacher.value.dni,
            subjects: teacher.value.subjects,
            doc: teacher.value.doc
        })
        
        teacher.value.teacherName = ""
        teacher.value.surname = ""
        teacher.value.dni = ""
        teacher.value.subjects = []
        teacher.value.doc = false
    }
</script>

<style scoped>

</style>