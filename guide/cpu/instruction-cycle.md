# The Instruction Cycle

When we ask the CPU to do something, we do that by way of an **instruction**. We give an instruction like, hey CPU - can you add these two numbers together? When the CPU is ready to work on that instruction, it sets off a cycle with 3 main stages:

1. [**Fetch**](#fetch) the data from memory
1. [**Decode**](#decode) that data to understand the instruction
1. [**Execute**](#execute) the instruction

<p align="center">
  <br />
  <img height="250" src="https://cloud-5lw2nkej5-hack-club-bot.vercel.app/0cycle.png">
</p>

## Fetch

In the first phase, the CPU must fetch the instruction data from **memory**, so it can see what you're asking it to do. Memory, also known as random access memory or RAM, is a type of short term storage your computer has. There are longer term storage places, like your hard drive, but we use memory when we need to keep something around temporarily.

<p align="center">
  <br />
  <img height="400" src="https://cloud-o0rjdm5vl-hack-club-bot.vercel.app/0shelves.png">
</p>
<br />

Let's imagine our CPU is a warehouse. Accessing your memory is kind of like going to a storage rack with boxes. Each box _(data)_ has a location _(memory address)_ where you can see what's inside the box _(read the data at that memory address)_. You can also take everything out of the box _(clear the contents at that memory address)_, and put new stuff in the box _(store new pieces of data at that memory address)_.

Here's something wild for you: in memory, all data is stored in the form of electricity. And because we store data as electricity, when your computer turns off and no more electricity is traveling to it, all of the things you have stored get cleared out! It's kind of like if every night when the warehouse closed, all of the packages got thrown out. That's why we refer to it as short term memory - we want to make sure to store important things in the hard drive, which is our longer term storage, lest it be thrown away.

Our box racks _(memory)_ has quite a bit of room to store our things - enough to hold large boxes. But, moving large boxes around the warehouse can be slow and cumbersome. So, for faster, smaller, and temporary storage, we have a set of numbered cubbyholes along the floor of the warehouse where we can place smaller packages. Those are our CPU's **registers**.

<p align="center">
  <br />
  <img height="250" src="https://cloud-9dq9biuyn-hack-club-bot.vercel.app/0cubbies.png">
</p>

Registers are where the CPU can store small pieces of data so that it can keep interacting with them. For example, let's say we need to add two numbers together.

First, the CPU retrieves the first number it needs for the equation. Since the CPU can really only do one thing at a time, it needs to put this number down in order to grab the next number. So it stores this first number into a register for the time being.

Next, the CPU grabs the second number in the equation. The CPU now has all the information it needs to add the two numbers together. It goes ahead and executes the adding instruction, passing that new number along, and then moves on to the next instruction it's given!

Now you may be asking yourself - why don't we store everything in the registers, since memory is slower? Well, we only have a limited amount of space in our registers. The actual size depends on your computer's hardware. Depending on the particular processor, you may get around 16 general purpose registers to store your data in. There are more registers than that, but some registers are used internally and can't be directly accessed.

Memory can easily hold over _15 million times_ the amount that registers can! Since computers have to process so much data, we can very quickly run out of space in our registers. So any data that we don't need to actively use for an instruction, we place in memory.

## Decode

Now that we've fetched the data, what does that data actually look like?

Well, as we've learned, the computer can only read numbers. So all of the data we store has to be represented in a way that the computer can read.

What those numbers represent include five broad categories, shown here with examples of what they look like:

1. Instruction opcodes (`add`)
1. Numeric values (`10`)
1. Letters (`"M"`)
1. Registers (`rax`)
1. Memory addresses (`0x12345678`)

The CPU will distinguish what type of data it's looking at when it gets to this decoding step.

Each CPU has a set of instructions that is built _physically into the chip_, which you can think of as a list of actions that coordinate with numbers that the CPU can do. Since the data grabbed from the fetch phase is just numbers, the CPU can decode the instruction by comparing the number it sees to the set instructions list.

| Number | Instruction |
| ------ | ----------- |
| 1      | `add`       |
| 2      | `sub`       |
| ...    | ...         |

The first part of the data it fetches is the **opcode**, which is the unique identifier for an action that the CPU can run. In the case of adding two numbers together, that opcode might look like `add`.

The next numbers that are fetched are the arguments to be executed. For a hypothetical example, let's say we have an instruction like:
```asm
add 3, 4
```

Our opcode is `add`, and our arguments are `3` and `4`!

## Execute

After the fetched data is decoded, the CPU now has an instruction that it can do.

If the instruction is arithmetic (like adding or subtracting) or logical (like comparing two digits to give a true or false), there's an extra stop at the **arithmetic-logic unit**, or **ALU**. This unit is responsible for doing math. Once it's finished math-ing, the ALU would then return a value, which is stored in a register until an instruction needs it.

<br />

---

<a href="/guide/cpu/communicating.md">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cloud-c4m75tmer-hack-club-bot.vercel.app/0back.svg">
    <img align="left" width="70" src="https://cloud-c4m75tmer-hack-club-bot.vercel.app/0back.svg" />
  </picture>
</a>

<p align="right">
  <em>
    <b>
      <a href="/guide/cpu/map.md">
        Let's look at this in practice →
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
