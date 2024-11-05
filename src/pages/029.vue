<script setup lang="ts">
// $('.searchfield').keyup(function() {
//   var $suggestions = $('.suggestions');
//   var text = $(this).val();
//   if(text.length){
//     $suggestions.html('').addClass('active');
//     $suggestions.append( $('<li />', {html: '<b>' + text + '</b>'}) );
//     $suggestions.append( $('<li />', {html: 'Veritatis et <b>' + text + '</b>'}) );
//     $suggestions.append( $('<li />', {html: 'ut aliquid ex <b>' + text + '</b> vero eos'}) );
//   } else {
//     $suggestions.html('').removeClass('active');
//   }
// });
</script>

<template>
  <div class="frame">
    <div class="search">
      <input type="text" class="searchfield" placeholder="Start typing ..." value="">
      <button type="button" class="button">
        <span class="fa fa-search" />
      </button>
      <ul class="suggestions clearfix" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 2px;
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  background: #5ca4ea;
  color: #fff;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.search {
  position: absolute;
  width: 260px;
  top: 180px;
  left: 70px;
  font-size: 0;
  background: #fff;
  box-shadow: 4px 8px 12px 0 rgba(0, 0, 0, 0.1);

  .searchfield {
    float: left;
    width: 205px;
    height: 40px;
    border: none;
    border-radius: 0;
    font-size: 13px;
    font-weight: 600;
    padding: 0 0 0 15px;
    background: #fff;
    color: #4d8dcb;
  }

  .button {
    position: relative;
    width: 40px;
    height: 40px;
    border: none;
    border-radius: 0;
    background: #fff;
    color: #5ca4ea;
    font-size: 20px;
    padding: 0;

    span {
      position: relative;
      top: -1px;
    }
  }

  .suggestions {
    background: #fff;
    font-size: 13px;
    font-weight: 400;
    line-height: 20px;
    padding: 0 15px;
    margin: 0;
    list-style: none;
    color: #6e6e6e;

    &.active {
      border-top: 1px solid #5ca4ea;
    }

    li {
      margin: 18px 0;
      padding: 0;
      cursor: pointer;

      &:hover {
        color: #4d8dcb;
      }

      b {
        font-weight: 600;
      }
    }
  }
}

.clearfix::before,
.clearfix::after {
  content: ' ';
  display: table;
}

.clearfix::after {
  clear: both;
}

.clearfix {
  *zoom: 1;
  /* Für den IE6 und IE7 */
}

*:focus {
  outline: none;
}

::-webkit-input-placeholder {
  /* WebKit, Blink, Edge */
  color: #a4b9ce;
}

:-moz-placeholder {
  /* Mozilla Firefox 4 to 18 */
  color: #a4b9ce;
  opacity: 1;
}

::-moz-placeholder {
  /* Mozilla Firefox 19+ */
  color: #a4b9ce;
  opacity: 1;
}

:-ms-input-placeholder {
  /* Internet Explorer 10-11 */
  color: #a4b9ce;
}

:placeholder-shown {
  /* Standard (https://drafts.csswg.org/selectors-4/#placeholder) */
  color: #a4b9ce;
}
</style>
