<template>
    <span class="val">
        <select name="value" v-model="item.remark" class="val-input" v-if="item.type === 'boolean'" @change="change">
            <option :value="true">true</option>
            <option :value="false">false</option>
        </select>
        <editable-text :isEdit="isEdit" v-else :value="item.remark" @change="(v) => {item.remark = v; this.change()}"></editable-text>
    </span>
</template>

<script>

import EditableText from "./EditableText.vue";
export default {
    name: 'EditValue',
    components: {EditableText},
    props: {item: {}, isEdit: false, type: String},
    data: function () {
        return {
        }
    },
    methods: {
        change:function() {
            this.$emit('change');
        }
    }
}
</script>