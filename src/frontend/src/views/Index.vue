<template>
  <div class="section__wrapper">
    <header class="header">
      <div class="header__logo">
        <a href="index.html" class="logo">
          <img
            src="../assets/img/logo.svg"
            alt="V!U!E! Pizza logo"
            width="90"
            height="40"
          />
        </a>
      </div>
      <div class="header__cart">
        <a href="cart.html">0 ₽</a>
      </div>
      <div class="header__user">
        <a href="#" class="header__login"><span>Войти</span></a>
      </div>
    </header>
    <main class="content">
      <form action="#" method="post">
        <div class="content__wrapper">
          <h1 class="title title--big">Конструктор пиццы</h1>
          <div class="content__dough">
            <div class="sheet">
              <h2 class="title title--small sheet__title">Выберите тесто</h2>
              <div class="sheet__content dough">
                <label
                  v-for="(paste, name) in dough"
                  :key="name"
                  :class="paste.image"
                  class="dough__input"
                >
                  <input
                    type="radio"
                    name="dought"
                    :value="paste.value"
                    class="visually-hidden"
                    checked
                  />
                  <b>{{ paste.name }}</b>
                  <span>{{ paste.description }}</span>
                </label>
              </div>
            </div>
          </div>
          <div class="content__diameter">
            <div class="sheet">
              <h2 class="title title--small sheet__title">Выберите размер</h2>
              <div class="sheet__content diameter">
                <label
                  v-for="(size, name) in sizes"
                  :key="name"
                  :title="size.name"
                  :class="size.icon"
                  class="diameter__input"
                >
                  <input
                    type="radio"
                    name="diameter"
                    :value="size.value"
                    class="visually-hidden"
                  />
                  <span>{{ size.name }}</span>
                </label>
              </div>
            </div>
          </div>
          <div class="content__ingridients">
            <div class="sheet">
              <h2 class="title title--small sheet__title">
                Выберите ингридиенты
              </h2>
              <div class="sheet__content ingridients">
                <div class="ingridients__sauce">
                  <p>Основной соус:</p>
                  <label
                    v-for="(sauce, name) in sauces"
                    :key="name"
                    :title="sauce.name"
                    class="radio ingridients__input"
                  >
                    <input
                      type="radio"
                      name="sauce"
                      :value="sauce.value"
                      checked
                    />
                    <span>{{ sauce.name }}</span>
                  </label>
                </div>
                <div class="ingridients__filling">
                  <p>Начинка:</p>
                  <ul class="ingridients__list">
                    <li
                      class="ingridients__item"
                      v-for="(ingredient, name) in ingredients"
                      :key="name"
                      :class="ingredient.icon"
                      :title="ingredient.name"
                    >
                      <span class="filling" :class="ingredient.icon">{{
                        ingredient.name
                      }}</span>
                      <div class="counter counter--orange ingridients__counter">
                        <button
                          type="button"
                          class="
                            counter__button
                            counter__button--disabled
                            counter__button--minus
                          "
                        >
                          <span class="visually-hidden">Меньше</span>
                        </button>
                        <input
                          type="text"
                          name="counter"
                          class="counter__input"
                          value="0"
                        />
                        <button
                          type="button"
                          class="counter__button counter__button--plus"
                        >
                          <span class="visually-hidden">Больше</span>
                        </button>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <div class="content__pizza">
            <label class="input">
              <span class="visually-hidden">Название пиццы</span>
              <input
                type="text"
                name="pizza_name"
                placeholder="Введите название пиццы"
              />
            </label>
            <div class="content__constructor">
              <div class="pizza pizza--foundation--big-tomato">
                <div class="pizza__wrapper">
                  <div class="pizza__filling pizza__filling--ananas"></div>
                  <div class="pizza__filling pizza__filling--bacon"></div>
                  <div class="pizza__filling pizza__filling--cheddar"></div>
                </div>
              </div>
            </div>
            <div class="content__result">
              <p>Итого: 0 ₽</p>
              <button type="button" class="button button--disabled" disabled>
                Готовьте!
              </button>
            </div>
          </div>
        </div>
      </form>
    </main>
  </div>
</template>

<script>
// Импортируем JSON данные.
import filling from "@/static/filling.json";
import ingredients from "@/static/ingredients.json";
import dough from "@/static/dough.json";
import sizes from "@/static/sizes.json";
import sauces from "@/static/sauces.json";

export default {
  name: "Index",
  data: () => ({
    filling,
    ingredients,
    dough,
    sizes,
    sauces,
  }),
};
</script>
<style scoped></style>
