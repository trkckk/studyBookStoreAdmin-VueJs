<template>
    <div class="container">
        <BootstrapCard>
            <BootstrapCardHeader header="Bookstore Admin Console"></BootstrapCardHeader>
            <Bootstrap-card-body>
                <BootstrapInputText label="Isbn" value="book.isbn">
                    <button class="btn btn-primary">Find Book</button>
                </BootstrapInputText>
                <BootstrapInputText label="Title" valuee="book.title"></BootstrapInputText>
                <BootstrapInputText label="Author" valuee="book.author"></BootstrapInputText>
                <BootstrapInputText label="Price" valuee="book.price"></BootstrapInputText>
                <BootstrapInputText label="Year" valuee="book.year"></BootstrapInputText>
                <BootstrapInputText label="Pages" valuee="book.pages"></BootstrapInputText>
                <BootstrapInputText label="Publisher" valuee="book.publisher"></BootstrapInputText>
                <div class="input-group">
                    <label class="form-label">Cover</label>
                    <img id="cover">
                    <input type="file" class="form-control">
                    <label>
                        <input type="file" style="display: none" class="form-control">
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
