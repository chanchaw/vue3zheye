<template>
    <div class="row">
        <div v-for="column in columnList" :key="column.id" class="col-4 mb-4">
            <div class="card h-100 shadow-sm">
                <img :src="column.avatar" :alt="column.title" class="card-img-top">
                <div class="card-body text-center">
                    <h5 class="card-title">{{column.title}}</h5>
                    <p class="card-text text-left">{{column.description}}</p>
                    <a href="#" class="btn btn-outline-primary">进入专栏</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { computed, ComputedRef, defineComponent,PropType } from 'vue';

export interface ColumnProps {
    id: number; title: string; avatar?: string; description: string;
}
export default defineComponent ({
    name: 'ColumnList',
    props: {
        list: {
            type: Array as PropType<ColumnProps[]>,
            require: true
        }
    },
    setup(props) {
        //下面的计算属性 columnList 的数据类型是：ComputedRef<ColumnProps[]>
        const columnList = computed(() => {
            return props.list.map(column => {
                if( !column.avatar )
                    column.avatar = require('@/assets/square.png')
                return column
            })
        })

        return { columnList }
    }
})
</script>