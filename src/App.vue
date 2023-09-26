<template>
  <div class="documentation">
    <h1 class="main-heading">   <img src="favicon.ico" alt="Favicon" class="favicon" />Vue 3 Documentation Blog</h1>

    <!-- Concept 1: Template Syntax -->
    <section>
      <h2>1. Template Syntax</h2>
      <p>
        Vue.js templates are used to render the DOM. They allow you to declaratively render dynamic data into the DOM.
      </p>

      <!-- a. Text Interpolation -->
      <div>
        <h3>a. Text Interpolation</h3>
        <p>Text interpolation is used to display dynamic content using double curly braces {{ }}.</p>
      </div>

      <!-- Example for a. Text Interpolation -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    {{ message }}
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      message: "Hello, Vue!",
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for a. Text Interpolation -->
      <div class="output">
        <button @click="showMessage">Show Message</button>
        <p>Message: {{ message }}</p>
      </div>
    </section>

    <!-- b. Raw HTML [v-html] -->
    <section>
      <h2>2. Raw HTML [v-html]</h2>
      <p>v-html allows rendering raw HTML content.</p>

      <!-- Example for b. Raw HTML [v-html] -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div v-html="htmlContent"&gt;&lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      htmlContent: "&lt;strong&gt;This is bold text&lt;/strong&gt;",
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for b. Raw HTML [v-html] -->
      <div class="output">
        <div v-html="htmlContent"></div>
      </div>
    </section>

    <!-- c. Attribute Bindings [v-bind:id] -->
    <section>
      <h2>3. Attribute Bindings [v-bind:id]</h2>
      <p>v-bind can be used to bind attributes like 'id'.</p>

      <!-- Example for c. Attribute Bindings [v-bind:id] -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div :id="dynamicId"&gt;Element with dynamic ID&lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      dynamicId: "unique-id",
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for c. Attribute Bindings [v-bind:id] -->
      <div class="output">
        <div :id="dynamicId">Element with dynamic ID</div>
      </div>
    </section>

    <!-- d. JavaScript expressions inside syntax i.e.{{ }} -->
    <section>
      <h2>4. JavaScript expressions inside syntax i.e.{{ }}</h2>
      <p>You can include JavaScript expressions within {{ }}.</p>

      <!-- Example for d. JavaScript expressions inside syntax i.e.{{ }} -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    Total: {{ num1 + num2 }}
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      num1: 5,
      num2: 10,
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for d. JavaScript expressions inside syntax i.e.{{ }} -->
      <div class="output">
        <p>Total: {{ num1 + num2 }}</p>
      </div>
    </section>
    <!-- Concept 2: Methods -->
    <section>
      <h2>2. Methods</h2>
      <p>
        Methods are functions defined in your Vue component that can be called to perform specific tasks or operations.
      </p>

      <!-- Example for 2. Methods -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="sayHello"&gt;Say Hello&lt;/button&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  methods: {
    sayHello() {
      alert("Hello!");
    },
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for 2. Methods -->
      <div class="output">
        <button @click="sayHello">Say Hello</button>
      </div>
    </section>

    <!-- Concept 3: Reactivity Fundamentals -->
    <section>
      <h2>3. Reactivity Fundamentals</h2>
      <p>
        Reactivity is at the core of Vue.js. Reactivity allows Vue to track changes to data and automatically
        update the DOM when data changes.
      </p>

      <!-- Example for 3. Reactivity Fundamentals [ref()] -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="incrementCounter"&gt;Increment Counter&lt;/button&gt;
    &lt;p&gt;Counter: {{ counter }}&lt;/p&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
import { ref } from "vue";

export default {
  setup() {
    const counter = ref(0);

    const incrementCounter = () => {
      counter.value++;
    };

    return {
      counter,
      incrementCounter,
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for 3. Reactivity Fundamentals [ref()] -->
      <div class="output">
        <button @click="incrementCounter">Increment Counter</button>
        <p>Counter: {{ counter }}</p>
      </div>
    </section>

    <!-- Example for 3. Reactivity Fundamentals [<script setup>] -->
    <section>
      <h3>3.1 Reactivity Fundamentals [<code>&lt;script setup&gt;</code>]</h3>
      <p>
        In Vue 3, you can also use the <code>&lt;script setup&gt;</code> syntax for simplified reactivity.
      </p>

      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="incrementCounter"&gt;Increment Counter&lt;/button&gt;
    &lt;p&gt;Counter: {{ counter }}&lt;/p&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script setup&gt;
import { ref } from "vue";

const counter = ref(0);

const incrementCounter = () => {
  counter.value++;
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for 3. Reactivity Fundamentals [<script setup>] -->
      <div class="output">
        <button @click="incrementCounter">Increment Counter</button>
        <p>Counter: {{ counter }}</p>
      </div>
    </section>

    <!-- Concept 4: Computed Properties -->
    <section>
      <h2>4. Computed Properties</h2>
      <p>
        Computed properties are values that are calculated based on other data properties. They are cached and
        automatically updated when their dependent properties change.
      </p>

      <!-- Example for 4. Computed Properties -->
      <div class="code-example">
        <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;p&gt;Width: {{ width }}px&lt;/p&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
import { ref, computed, onMounted, onUnmounted } from "vue";

export default {
  setup() {
    const windowWidth = ref(window.innerWidth);

    const width = computed(() => windowWidth.value);

    const handleResize = () => {
      windowWidth.value = window.innerWidth;
    };

    onMounted(() => {
      window.addEventListener("resize", handleResize);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", handleResize);
    });

    return {
      width,
    };
  },
};
&lt;/script&gt;</code></pre>
      </div>

      <!-- Output for 4. Computed Properties -->
      <div class="output">
        <p>Width: {{ width }}px</p>
      </div>
    </section>

    <!-- Concept 5: Class and Style Bindings -->
    <section>
      <h2>5. Class and Style Bindings</h2>
      <p>
        Vue allows you to dynamically bind classes and inline styles to elements based on data properties.
      </p>

      <!-- a. Binding HTML class [v-bind:class] -->
      <section>
        <h3>5.1 a. Binding HTML class [v-bind:class]</h3>
        <p>You can dynamically add or remove classes using <code>v-bind:class</code>.</p>

        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;div :class="{ 'active': isActive }"&gt;Active&lt;/div&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      isActive: false,
    };
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Output for 5.1 a. Binding HTML class [v-bind:class] -->
        <div class="output">
          <div :class="{ 'active': isActive }">Active</div>
        </div>
      </section>

      <!-- b. Binding Inline Styles [v-bind:style] -->
      <section>
        <h3>5.2 b. Binding Inline Styles [v-bind:style]</h3>
        <p>You can dynamically set inline styles using <code>v-bind:style</code>.</p>

        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;div :style="{ 'color': textColor, 'font-size': fontSize + 'px' }"&gt;Styled Text&lt;/div&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      textColor: "blue",
      fontSize: 20,
    };
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Output for 5.2 b. Binding Inline Styles [v-bind:style] -->
        <div class="output">
          <div :style="{ 'color': textColor, 'font-size': fontSize + 'px' }">Styled Text</div>
        </div>
      </section>
    </section>

    <!-- Concept 6: List Rendering -->
    <section>
      <h2>6. List Rendering</h2>
      <p>
        Vue provides the <code>v-for</code> directive for rendering lists of items.
      </p>

      <!-- a. v-for with an Object -->
      <section>
        <h3>6.1 a. v-for with an Object</h3>
        <p>You can use <code>v-for</code> to loop through the properties of an object.</p>

        <!-- Example -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;ul&gt;
      &lt;li v-for="(value, key) in user"&gt;{{ key }}: {{ value }}&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      user: {
        name: "John Doe",
        age: 30,
        email: "john@example.com",
      },
    };
  },
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Renders a list of object properties. -->
      </section>

      <!-- b. v-for with a Range -->
      <section>
        <h3>6.2 b. v-for with a Range</h3>
        <p>You can use <code>v-for</code> to create a list by iterating through a range of numbers.</p>

        <!-- Example -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;ul&gt;
      &lt;li v-for="n in 5"&gt;Item {{ n }}&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/template&gt;</code></pre>
        </div>
        <!-- Output: Renders a list of items using a range. -->
      </section>

    </section>


    <!-- Concept 7: Event Handling: Listening to Events [v-on:click] -->
    <section>
      <h2>7. Event Handling: Listening to Events [v-on:click]</h2>
      <p>
        Vue allows you to listen to events and trigger functions when events occur.
      </p>

      <!-- a. Inline Handlers -->
      <section>
        <h3>7.1 a. Inline Handlers</h3>
        <p>You can add event listeners directly in the template using <code>@</code>.</p>

        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="showAlert"&gt;Show Alert&lt;/button&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  methods: {
    showAlert() {
      alert("Button Clicked!");
    },
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Output for 7.1 a. Inline Handlers -->
        <div class="output">
          <button @click="showAlert">Show Alert</button>
        </div>
      </section>

      <!-- b. Method Handlers -->
      <section>
        <h3>7.2 b. Method Handlers</h3>
        <p>You can call methods to handle events.</p>

        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="sayHello"&gt;Say Hello&lt;/button&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  methods: {
    sayHello() {
      alert("Hello!");
    },
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Output for 7.2 b. Method Handlers -->
        <div class="output">
          <button @click="sayHello">Say Hello</button>
        </div>
      </section>
    </section>

    <!-- Concept 8: Form Input Bindings -->
    <section>
      <h2>8. Form Input Bindings</h2>
      <p>
        Vue provides the <code>v-model</code> directive for two-way data binding with form elements.
      </p>

      <!-- a. v-model with various input types -->
      <section>
        <h3>8.1 a. v-model with various input types</h3>
        <p>You can use <code>v-model</code> with different input types like text, checkbox, radio, select, and textarea.
        </p>

        <!-- Text Input -->
        <div class="code-example">
          <pre><code>&lt;input type="text" v-model="textValue" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="text" v-model="textValue" />
        </div>

        <!-- Checkbox -->
        <div class="code-example">
          <pre><code>&lt;input type="checkbox" v-model="isChecked" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="checkbox" v-model="isChecked" />
        </div>

        <!-- Radio -->
        <div class="code-example">
          <pre><code>&lt;input type="radio" value="option1" v-model="radioValue" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="radio" value="option1" v-model="radioValue" />
        </div>

        <!-- Select -->
        <div class="code-example">
          <pre><code>&lt;select v-model="selectedOption"&gt;
  &lt;option value="option1"&gt;Option 1&lt;/option&gt;
  &lt;option value="option2"&gt;Option 2&lt;/option&gt;
&lt;/select&gt;</code></pre>
        </div>
        <div class="output">
          <select v-model="selectedOption">
            <option value="option1">Option 1</option>
            <option value="option2">Option 2</option>
          </select>
        </div>

        <!-- Textarea -->
        <div class="code-example">
          <pre><code>&lt;textarea v-model="textareaValue"&gt;&lt;/textarea&gt;</code></pre>
        </div>
        <div class="output">
          <textarea v-model="textareaValue"></textarea>
        </div>
      </section>

      <!-- b. v-model modifiers -->
      <section>
        <h3>8.2 b. v-model modifiers</h3>
        <p>You can use modifiers like <code>.lazy</code>, <code>.number</code>, and <code>.trim</code> with
          <code>v-model</code> for specific behaviors.
        </p>

        <!-- .lazy Modifier -->
        <div class="code-example">
          <pre><code>&lt;input type="text" v-model.lazy="lazyValue" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="text" v-model.lazy="lazyValue" />
        </div>

        <!-- .number Modifier -->
        <div class="code-example">
          <pre><code>&lt;input type="text" v-model.number="numberValue" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="text" v-model.number="numberValue" />
        </div>

        <!-- .trim Modifier -->
        <div class="code-example">
          <pre><code>&lt;input type="text" v-model.trim="trimmedValue" /&gt;</code></pre>
        </div>
        <div class="output">
          <input type="text" v-model.trim="trimmedValue" />
        </div>
      </section>
    </section>

    <!-- Concept 9: Watchers -->
    <section>
      <h2>9. Watchers</h2>
      <p>
        Watchers allow you to react to changes in data properties and perform custom actions.
      </p>

      <!-- Example -->
      <section>
        <h3>9.1 Example</h3>
        <p>Here's an example of using a watcher to respond to changes in a data property.</p>

        <!-- Watcher Code -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;input type="text" v-model="message" /&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  data() {
    return {
      message: "",
    };
  },
  watch: {
    message(newValue, oldValue) {
      console.log(`Message changed from "${oldValue}" to "${newValue}"`);
    },
  },
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Console log message when the input value changes. -->
      </section>
    </section>

    <!-- Concept 10: Components -->
    <section>
      <h2>10. Components</h2>
      <p>
        Components in Vue.js allow you to create reusable and modular pieces of UI.
      </p>

      <!-- a. Props -->
      <section>
        <h3>10.1 a. Props</h3>
        <p>Props allow you to pass data from a parent component to a child component.</p>

        <!-- Parent Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;my-component :message="parentMessage" /&gt;
  &lt;/div&gt;
&lt;/template&gt;</code></pre>
        </div>

        <!-- Child Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;p&gt;Message from parent: {{ message }}&lt;/p&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  props: {
    message: String,
  },
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Displays the message from the parent component. -->
      </section>

      <!-- b. Events [$emit] -->
      <section>
        <h3>10.2 b. Events [$emit]</h3>
        <p>Child components can emit custom events that parent components can listen to.</p>

        <!-- Child Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;button @click="sendEvent"&gt;Send Event&lt;/button&gt;
  &lt;/div&gt;
&lt;/template&gt;

&lt;script&gt;
export default {
  methods: {
    sendEvent() {
      this.$emit('custom-event', 'Hello from child!');
    },
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Parent Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;my-component @custom-event="handleCustomEvent" /&gt;
  &lt;/div&gt;

&lt;script&gt;
import MyComponent from "./MyComponent.vue";

export default {
  components: {
    MyComponent,
  },
  methods: {
    handleCustomEvent(message) {
      alert("Custom Event Received: " + message);
    },
  },
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Displays an alert when the custom event is received. -->
      </section>

      <!-- c. Slots -->
      <section>
        <h3>10.3 c. Slots</h3>
        <p>Slots allow you to pass content from a parent component to a child component for flexible rendering.</p>

        <!-- Parent Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;my-component&gt;
      &lt;h2&gt;Slot Content&lt;/h2&gt;
      &lt;p&gt;This content is passed via a slot.&lt;/p&gt;
    &lt;/my-component&gt;
  &lt;/div&gt;

&lt;script&gt;
import MyComponent from "./MyComponent.vue";

export default {
  components: {
    MyComponent,
  },
};
&lt;/script&gt;</code></pre>
        </div>

        <!-- Child Component -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;slot&gt;&lt;/slot&gt;
  &lt;/div&gt;

&lt;script&gt;
export default {
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Renders the content passed via the slot. -->
      </section>
    </section>

    <!-- Concept 11: Router -->
    <section>
      <h2>11. Router</h2>
      <p>
        Vue Router allows you to add routing to your Vue.js applications for navigation.
      </p>

      <!-- Example -->
      <section>
        <h3>11.1 Example</h3>
        <p>Here's an example of setting up routing in a Vue.js application.</p>

        <!-- Router Code -->
        <div class="code-example">
          <pre><code>&lt;template&gt;
  &lt;div&gt;
    &lt;router-link to="/home"&gt;Home&lt;/router-link&gt;
    &lt;router-link to="/about"&gt;About&lt;/router-link&gt;
    &lt;router-view&gt;&lt;/router-view&gt;
  &lt;/div&gt;

&lt;script&gt;
import { createRouter, createWebHistory } from 'vue-router';
import Home from './views/Home.vue';
import About from './views/About.vue';

const routes = [
  { path: '/home', component: Home },
  { path: '/about', component: About },
];

const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default {
  router,
};
&lt;/script&gt;</code></pre>
        </div>
        <!-- Output: Renders different views based on the route. -->
      </section>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Hello, Vue!",
      htmlContent: "<strong>This is bold text</strong>",
      dynamicId: "unique-id",
      num1: 5,
      num2: 10,
    };
  },
  methods: {
    showMessage() {
      alert(this.message);
    },
  },
};
</script>

<style scoped>
.documentation {
  font-family: Arial, sans-serif;
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
}

h1.main-heading {
  text-align: center;
  font-size: 34px;
  margin-bottom: 30px;
  display: flex;
  justify-content: center;
  align-items: baseline;
  background-color: grey;
  padding: 5px;
  border-radius: 20px;
}

h2 {
  margin-top: 30px;
  font-size: 20px;
}

h3 {
  margin-top: 20px;
  font-size: 18px;
}

p {
  margin-top: 10px;
}

.code-example {
  background-color: #f2f2f2;
  padding: 10px;
  margin-top: 10px;
}

.code-example pre {
  white-space: pre-wrap;
}

.output {
  margin-top: 20px;
}

button {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #0056b3;
}

/* Add more styles as needed for specific elements */
</style>
