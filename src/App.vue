<template>
  <div id="app" class="index">
    <header class="header">
      <div class="row">
        <div class="columns small-12">
          <a href="/" class="header__logo">
            <img src="/logo.png" alt="Logo cukierni">
          </a>
        </div>
      </div>
    </header>
    <div class="hero">
      <img src="/img/about.jpeg" alt="">
    </div>
    <section class="about">
      <div class="row">
        <div class="columns small-12">
          <h1 class="base-header">Kawiarnia Amadeo</h1>
        </div>
        <div class="columns small-12">
          <div class="about__content">
            <p>
              Kawiarnia Amadeo istnieje od kilkunastu lat na rynku, lokal znajduje się w centrum Chorzowa przy ul. Wolności. Z biegiem czasu, nasz lokal stał się miejscem idealnym do spędzenia czasu z rodziną, przyjaciółmi, a nawet w pojedynkę. Nasi klienci bardzo chętnie organizują u nas małe imprezy okolicznościowe. W naszej ofercie znajdziecie Państwo wyśmienite ciasta, lody i desery, pyszną kawę, sezonowe specjały i wiele, wiele innych. Przyjmujemy zamówienia torty okolicznościowe. Serdecznie zapraszamy do odwiedzenia naszego lokalu!
            </p>
          </div>
        </div>
      </div>
    </section>
    <section class="products">
      <div class="row">
        <div class="columns small-12">
          <h2 class="base-header">Produkty</h2>
        </div>
        <div v-for="product in products" :key="product.name" class="columns small-12 medium-6 large-3">
          <div class="products__item">
            <img :src="require(`../public/img/products/${product.img}.png`)" :alt="products.name">
            <h3>{{ product.name }}</h3>
          </div>
        </div>
      </div>
    </section>
    <footer class="footer">
      <div class="row">
        <div class="columns small-12 medium-5 large-5">
          <div class="footer__address">
            <span class="footer__bold">Cukiernia Amadeo</span>
            <span>ul. Wolności 66</span>
            <span>41-500 Chorzów</span>
            <span>tel: 501 091 881</span>
          </div>
        </div>
        <div class="columns small-12 medium-5 large-5">
          <div class="footer__opening">
            <span class="footer__bold">Godziny otwarcia:</span>
            <span>poniedziałek-niedziela: 9:00-20:00</span>
          </div>
        </div>
        <div class="columns small-12 medium-2 footer__facebook">
          <a href="https://www.facebook.com/kawiarnia.amadeo" rel="nofollow noopener" target="_blank">
            <svg width="24" height="24" viewBox="0 0 24 24">
              <path id="facebook" d="M24,12.073A12,12,0,1,0,10.125,23.927V15.542H7.078v-3.47h3.047V9.43c0-3.007,1.792-4.669,4.533-4.669A18.418,18.418,0,0,1,17.344,5V7.949H15.83a1.735,1.735,0,0,0-1.956,1.874v2.25H17.2l-.532,3.47h-2.8v8.385A12,12,0,0,0,24,12.073Z" transform="translate(0 -0.073)" fill="#fff" stroke="#000" />
            </svg>
          </a>
        </div>
      </div>
    </footer>
    <div class="banner">
      <div class="row">
        <div class="columns small-12 medium-6 large-6">
          <img src="/img/pfr.jpeg" alt="">
        </div>
        <div class="columns small-12 medium-6 large-6">
          <img src="/img/fe-rp.jpeg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      products: [
        {
          name: 'Ciasta',
          img: 'ciasta'
        },
        {
          name: 'Torty',
          img: 'torty'
        },
        {
          name: 'Desery',
          img: 'desery'
        },
        {
          name: 'Napoje',
          img: 'napoje'
        },
      ]
    }
  }
}
</script>

<style lang="scss">
.header {
  box-shadow: 0 0 1em rgba(#000, 0.1);
  &__logo {
    width: 150px;
    height: 115px;
    display: block;
    margin: 0 auto;
    position: relative;
    overflow: hidden;

    @include desktop {
      width: 180px;
      height: 130px;
    }

    img {
      width: 100%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -56%);
    }
  }
}

.base-header {
  font-size: 20px;
  display: block;
  width: 100%;
  margin-bottom: 0;
  text-align: center;
  padding: 15px 0;
  font-family: 'Playfair Display', serif;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 1px;

  @include desktop {
    font-size: 24px;
    padding: 30px 0;
  }
}

.vertical-center {
  @include tablet {
    text-align: center;
    margin-top: 140px;
  }
}

.products {
  padding: 40px 0;
  background: #f9f7f6;
  
  &__item {
    text-align: center;
    margin-top: 40px;
    margin-bottom: 30px;

    @include desktop {
      margin-bottom: 20px;
      margin-top: 20px;
    }

    img {
      box-shadow: 0 0 1em rgba(#000, 0.1);
      border-radius: 50%;
      width: 70%;
      margin: 0 auto;
    }

    h3 {
      margin-top: 20px;
      font-family: 'Playfair Display', serif;
      font-weight: 300;
      font-size: 1.4em;
      @include desktop {
        font-size: 1.2em;
        margin-top: 30px;
      }
    }
  }
}

.hero {
  width: 100%;
  padding-bottom: 30%;
  position: relative;
  overflow: hidden;

  @include desktop {
    padding-bottom: 16%;
  }

  img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -65%);
    width: 100%;
  }
}

.about {
  margin-top: 40px;
  margin-bottom: 60px;

  @include desktop {
    margin-top: 90px;
    margin-bottom: 120px;    
  }

  &__content {
    p {
      margin-top: 0;
      text-align: center;

      @include desktop {
        text-align: left;
        column-count: 2;
      }
    }
  }
}

.ue-project {
  margin-top: 40px;
  margin-bottom: 40px;

  @include desktop {
    margin-top: 60px;
    margin-bottom: 60px;
  }
}

.footer {
  border-top: 1px solid rgba(#000, 0.1);
  padding: 20px 0;

  @include desktop {
    padding: 40px 0;
  }

  &__address,
  &__opening {
    span {
      display: block;
      margin-left: 3px;
    }
  }

  &__opening {
    margin-top: 40px;

    @include tablet {
      margin-top: 0;
    }
  }

  &__bold {
    margin-bottom: 8px;
    font-size: 1.2em;
    margin-left: 0 !important;
  }

  &__facebook {
    display: flex;
    justify-content: center;

    @include desktop {
      justify-content: flex-end;
    }
  }
}
</style>
