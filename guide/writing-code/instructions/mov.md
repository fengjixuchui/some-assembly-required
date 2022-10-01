# I Like The Way You Mov

It's the moment you've been waiting for, folks. We're going to write some code!

First, let's give an example in JavaScript to help explain what we're doing.

```js
// JavaScript
let a = 5;
```

_In JavaScript, we're setting the value of a variable, `a`, to the number `5`._

As we talked about earlier, in higher level programming, you'd use a **variable** to store data for later use. You can think of **registers as the variables of assembly language**.

```asm
; X86-64 Intel Syntax Assembly
mov rax, 5;
```
_In assembly, we're setting the value of a register, `rax`, to the number `5`._

We're using a **mov** instruction here (short for "Move"). This moves the value on the right side (`5`) _into_ the register on the left side (`rax`).

---

Now, variables and registers are quite similar in this regard, but there are some key differences to remember.

With **variables**, you can create an _unlimited amount_ of them and _name them whatever you'd like_.

**Registers**, on the other hand, are _limited_ to a set determined by the processor. You also _can't name them_, they're like already set up variables that you can change the contents of.

```js
// JavaScript
let a = 3;
let b = a;
```
_At the end of this, `b` will contain the value `3`._

```asm
; X86-64 Intel Syntax Assembly
mov rax, 3;
mov rbx, rax;
```
<details>
<summary><i>At the end of this example, what do you think the value of <code>rbx</code> will be?</i></summary>
<br />
<i>In our previous assembly example, we set the value of the <code>rax</code> register to a number. In this example, we set the value one register to the value of another register. At the end of this, <code>rbx</code> will contain the value <code>3</code>.</i>
</details>

---

One last `mov` example for you, just to drive the point home.

```js
// JavaScript
let a = 3;
let b = 5;

a = b;
```
_Even though we set `a` to `3` in the beginning, at the end of this example, `a` is `5` since we set `a` to the contents of `b`._

```asm
; X86-64 Intel Syntax Assembly
mov rax, 3;
mov rbx, 5;

mov rax, rbx;
```

<details>
<summary><i>At the end of this example, what do you think the value of <code>rax</code> will be?</i></summary>
<br />
<i>Even though we set <code>rax</code> to <code>3</code> in the beginning, at the end of this example, <code>rax</code> is <code>5</code> since we set <code>rax</code> to the contents of <code>rbx</code>.</i>
</details>

<br />

---

<a href="/guide/writing-code/registers.md">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cloud-c4m75tmer-hack-club-bot.vercel.app/0back.svg">
    <img align="left" width="70" src="https://cloud-c4m75tmer-hack-club-bot.vercel.app/0back.svg" />
  </picture>
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/writing-code/instructions/math.md">
        What else can we do? →
      </a>
    </b>
  </em>
</p>

---

<p align="center">
  <a href="https://hackclub.com/">
    <img width="35" src="https://cloud-l0g1cgz4b-hack-club-bot.vercel.app/0h.png"><br/>
    Made with love by Hack Club
  </a>
</p>
