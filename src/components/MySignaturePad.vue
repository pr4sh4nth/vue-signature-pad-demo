<template>
  <div>
    <VueSignaturePad
      ref="signaturePad"
      width="700px"
      height="500px"
      class="signaturePad"
    />
    <div class="buttonSet">
      <button @click="save">Save</button>
      <button @click="undo">Undo</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "MySignaturePad",
  props: {},
  methods: {
    undo() {
      this.$refs.signaturePad.undoSignature();
    },
    save() {
      const { isEmpty, data } = this.$refs.signaturePad.saveSignature();
      console.log(isEmpty);
      console.log(data);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.signaturePad {
  margin: 0 auto;
  border: black 3px solid;
}
.buttonSet {
  max-width: 100%;
  margin: 10px 0;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
</style>
