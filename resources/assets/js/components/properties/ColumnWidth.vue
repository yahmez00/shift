<template>
    <div class="mb-2">
        <label class="style-panel-label">Column Width</label>

        <b-form-select v-model="selectedWidth" @change="setColumnWidth">
            <option v-for="(width, index) in widths" :value="width.value" :key="index">
                {{ width.text }}
            </option>
        </b-form-select>
    </div>
</template>

<script>
export default {
    name: "ColumnWidth",

    computed: {
        selectedWidth: {
            get() {
                return this.$store.getters.getSelectedElement.columnWidth;
            },
            set(width) {
                this.$store.commit('setComponentProperty', { property: 'columnWidth', value: width });
            }
        }
    },

    data() {
        return {
            widths: [
                {
                    text: 'Twelve Columns',
                    value: 12,
                },
                {
                    text: 'Eleven Columns',
                    value: 11,
                },
                {
                    text: 'Ten Columns',
                    value: 10,
                },
                {
                    text: 'Nine Columns (3/4)',
                    value: 9,
                },
                {
                    text: 'Eight Columns (2/3)',
                    value: 8,
                },
                {
                    text: 'Seven Columns',
                    value: 7,
                },
                {
                    text: 'Six Columns (1/2)',
                    value: 6,
                },
                {
                    text: 'Five Columns',
                    value: 5,
                },
                {
                    text: 'Four Columns (1/3)',
                    value: 4,
                },
                {
                    text: 'Three Columns (1/4)',
                    value: 3,
                },
                {
                    text: 'Two Columns',
                    value: 2,
                },
                {
                    text: 'One Column',
                    value: 1,
                },
            ]
        }
    },

    methods: {
        isSelected(width) {
            return this.$store.getters.getSelectedElement.columnWidth === width;
        },

        setColumnWidth(value) {
            this.$store.commit('setComponentProperty', { property: 'columnWidth', value: value });
        }
    }
}
</script>

