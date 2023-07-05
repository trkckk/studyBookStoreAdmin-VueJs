<template>
    <div class="container">
        <BootstrapCard>
            <BootstrapCardHeader header="Bookstore Admin Console"></BootstrapCardHeader>
            <Bootstrap-card-body>
                <BootstrapInputText label="Isbn" value="book.isbn">
                    <button class="btn btn-primary">Find Book</button>
                </BootstrapInputText>
                <BootstrapInputText label="Title" @change="book.title=$event.target.value" :value="book.title"></BootstrapInputText>
                <BootstrapInputText label="Author" @change="book.author=$event.target.value" :value="book.author"></BootstrapInputText>
                <BootstrapInputText label="Price" @change="book.price=$event.target.value" :value="book.price"></BootstrapInputText>
                <BootstrapInputText label="Year" @change="book.year=$event.target.value" :value="book.year"></BootstrapInputText>
                <BootstrapInputText label="Pages" @change="book.pages=$event.target.value" :value="book.pages"></BootstrapInputText>
                <BootstrapInputText label="Publisher" @change="book.publisher=$event.target.value" :value="book.publisher"></BootstrapInputText>
                <div class="input-group">
                    <label class="form-label">Cover</label>
                    <img id="cover" v-bind:src="book.cover">
                    <input type="file" class="form-control">
                    <label>
                        <input type="file" style="display: none" v-on:change="selectFile"  class="form-control">1
                        <span class="btn btn-info">File</span>
                    </label>
                </div>
                <div class="input-group">
                    <button class="btn btn-success">Create Book</button>
                    <button class="btn btn-warning">Update Book</button>
                    <button class="btn btn-danger">Delete Book</button>
                </div>
            </Bootstrap-card-body>
        </BootstrapCard>

    </div>

</template>

<script>
import BootstrapCard from "@/components/BootstrapCard";
import BootstrapCardHeader from "@/components/BootstrapCardHeader";
import BootstrapCardBody from "@/components/BootstrapCardBody";
import Book from "@/model/book";
import BootstrapInputText from "@/components/BootstrapInputText";
export default {
  name: 'BookstoreAdmin',
    components: {BootstrapInputText, BootstrapCardBody, BootstrapCardHeader, BootstrapCard},
    props: {
    msg: String
  },
    methods:{
      selectfile(event){
          let file = event.target.files[0];
          let reader = new FileReader();
          reader.readAsDataURL(file);
          reader.onload = (event) => {
              this.book.cover = event.target.result;
          }
      }
    }
    ,
    data:function () {
      return{
          book: new Book()
      }
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
