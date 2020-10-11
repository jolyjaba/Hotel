<template>
  <div v-if="type === 'default'">
    <p class="dropdown__label">
      {{ label }}
    </p>
    <div class="dropdown">
      <input type="checkbox" name="dropdown" id="dropdown" />
      <label for="dropdown" class="dropdown__select">
        <div class="dropdown__border">
          <div class="dropdown__placeholder">
            {{ placeholder }}
          </div>
          <div class="dropdown__trigger">
            <img src="@/assets/svg/dropDown.svg" alt="dropdown trigger" />
          </div>
        </div>
      </label>
      <div class="dropdown__options">
        <div class="dropdown__option">
          <p>Спальни</p>
          <div class="dropdown__counter">
            <div class="decrease"><p>-</p></div>
            <div class="count"><p>2</p></div>
            <div class="increase"><p>+</p></div>
          </div>
        </div>
        <div class="dropdown__option">
          <p>Спальни</p>
          <div class="dropdown__counter">
            <div class="decrease disabled"><p>-</p></div>
            <div class="count"><p>0</p></div>
            <div class="increase"><p>+</p></div>
          </div>
        </div>
        <div class="dropdown__option">
          <p>Спальни</p>
          <div class="dropdown__counter">
            <div class="decrease disabled"><p>-</p></div>
            <div class="count"><p>0</p></div>
            <div class="increase"><p>+</p></div>
          </div>
        </div>
        <div class="dropdown__footer">
          <div class="dropdown__clear">очистить</div>
          <div class="dropdown__apply">применить</div>
        </div>
      </div>
    </div>
  </div>
  <div v-else class="date-dropdown">
    <input type="checkbox" name="dropdownDate" id="dropdownDate" />
    <div class="date__arrive">
      <p class="dropdown__label">прибытие</p>
      <div class="dropdown dropdown--date">
        <label for="dropdownDate" class="dropdown__select">
          <div class="dropdown__border">
            <div class="dropdown__placeholder">
              {{ placeholder }}
            </div>
            <div class="dropdown__trigger">
              <img src="@/assets/svg/dropDown.svg" alt="dropdown trigger" />
            </div>
          </div>
        </label>
      </div>
    </div>
    <div class="date__depart">
      <p class="dropdown__label">выезд</p>
      <div class="dropdown dropdown--date">
        <label for="dropdownDate" class="dropdown__select">
          <div class="dropdown__border">
            <div class="dropdown__placeholder">
              {{ placeholder }}
            </div>
            <div class="dropdown__trigger">
              <img src="@/assets/svg/dropDown.svg" alt="dropdown trigger" />
            </div>
          </div>
        </label>
      </div>
    </div>
    <div class="dropdown__calendar">Calendar</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    placeholder: { type: String, required: true },
    label: { type: String, required: false },
    type: { type: String, required: true }
  }
});
</script>

<style lang="scss" scoped>
@import "@/components/Fonts_Colors.scss";

.date-dropdown {
  display: flex;
  justify-content: space-between;
  position: relative;
  z-index: 10;
  & > input {
    display: none;
    &:checked ~ .dropdown__calendar {
      transform: translateY(-9.44px);
      visibility: visible;
      opacity: 1;
      z-index: 1;
      transition-delay: 0s, 0s, 0.3s;
    }
  }
}

.dropdown {
  $self: &;
  position: relative;
  z-index: 1;
  margin-bottom: 15px;
  &__calendar {
    position: absolute;
    width: 100%;
    background-color: #fff;
    transition: all 0.3s ease-in-out 0s, visibility 0s linear 0.3s,
      z-index 0s linear 0.01s;
    top: 100%;
    transform: translateY(-2em);
    visibility: hidden;
    opacity: 0;
    z-index: -1;
    border: 1px solid rgba(31, 32, 65, 0.25) {
      radius: 4px;
    }
    box-shadow: 0px 10px 20px rgba(31, 32, 65, 0.05);
    padding: 20px;
  }
  &--date {
    max-width: 150px;
    #{$self}__border {
      &:hover {
        border-color: rgba(31, 32, 65, 0.25);
      }
    }
  }
  &__footer {
    display: flex;
    justify-content: space-between;
    margin: 3.5px;
  }
  &__clear,
  &__apply {
    @extend %H3;
    color: $purple;
    text-transform: uppercase;
    margin: 13px 0 6px 7px;
    cursor: pointer;
  }
  &__label {
    @extend %H3;
    text-transform: uppercase;
    text-align: start;
    margin: 5px 0;
  }
  &__options {
    padding: 3.5px;
    background-color: #fff;
    position: absolute;
    width: 100%;
    display: flex;
    transition: all 0.3s ease-in-out 0s, visibility 0s linear 0.3s,
      z-index 0s linear 0.01s;
    top: 100%;
    transform: translateY(-2em);
    visibility: hidden;
    opacity: 0;
    z-index: -1;
    flex-direction: column;
    border: 1px solid rgba(31, 32, 65, 0.5) {
      bottom: {
        left-radius: 4px;
        right-radius: 4px;
      }
      top: {
        width: 0px;
      }
    }
  }
  & > input {
    display: none;
    &:checked ~ label {
      .dropdown__border {
        border: {
          color: rgba(31, 32, 65, 0.5);
          bottom: {
            left-radius: 0px;
            right-radius: 0px;
          }
        }
      }
    }
    &:checked ~ .dropdown__options {
      transform: translateY(0%);
      visibility: visible;
      opacity: 1;
      z-index: 1;
      transition-delay: 0s, 0s, 0.3s;
    }
  }
  &__option {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 3.5px;
    & > p {
      @extend %H3;
      text-transform: uppercase;
      margin-left: 7px;
      line-height: unset;
    }
  }
  &__counter {
    display: flex;
    .count {
      & > p {
        @extend %H3;
        line-height: unset;
      }
    }
    .decrease {
      &.disabled {
        opacity: 0.5;
        cursor: unset;
        pointer-events: none;
      }
    }
    .decrease,
    .increase {
      border: 1px solid rgba(31, 32, 65, 0.25) {
        radius: 22px;
      }
      color: rgba(31, 32, 65, 0.5);
      cursor: pointer;
    }
    .decrease,
    .increase,
    .count {
      width: 30px;
      height: 30px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
  &__border {
    display: flex;
    height: 44px;
    justify-content: space-between;
    cursor: pointer;
    background-color: #fff;
    @extend %Transition;
    border: 1px solid rgba(31, 32, 65, 0.25) {
      radius: 4px;
    }
    &:hover {
      border-color: rgba(31, 32, 65, 0.5);
    }
  }
  &__trigger {
    width: 44px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    img {
      pointer-events: none;
      user-select: none;
    }
  }
  &__placeholder {
    margin: 8px 0px 8px 14px;
    max-width: 160px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    opacity: 0.75;
  }
}
</style>
