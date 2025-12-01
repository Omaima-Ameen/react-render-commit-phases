When you're building React apps, there's always this moment where you pause and think,
Wait… how does React actually decide what needs to update?

When does it re-run a whole component, and when does it actually touch the real DOM?
That’s exactly where the whole render phase vs commit phase story starts making sense.

## So , What is Render Phase?
This is the part where react decides what changes need to be made to the UI to make it look "good"
that means, It's the pure calculation phase that doesn't dirctly interact with the DOM

## This phase has a few super important traits:

**Pure Functions**:- It figures out what the next UI should look like without causing any side effects. Your components run like pure functions...React reads the props, processes the state, and builds a fresh virtual DOM snapshot of what the UI ought to be.

**Interruptibility**:- In React(after recent updates) , the render phase can be paused, interrupted or even restarted to prioritize more urgent updates.

**Output**:-React comes out of the render phase with a blueprint of the UI — a clean description of how everything should look. But nothing is applied yet. No DOM changes. No visual updates. Just a calculated plan waiting for the commit phase to bring it to life.

**When a component’s state updates, React re-runs the entire component tree in memory to figure out what’s different. It’s like React taking a fresh snapshot of the UI to compare what changed before touching the real DOM.**

## Now What does the Commit Phase do?
It's the mutation Phase of React's rendering process, which means React takes all the calculated changes from the render phase and applies them to the real UI.This is the moment where the virtual plan becomes actual DOM updates - attaching, updating, or removing elements, running layout effects, and making the UI visibly change on the screen.

## Important traits of Commit Phase:

**Dom Updates**:- React writes the calculated changes like creating, updating, or removing DOM elements.

**Side Effects**:- React executes lifecycle methods such as *componentDidMount*, *componentDidUpdate*, or effects defined using *useEffect*.

**Non-Interruptibe**:- Unlike the render phase, the commit phase can’t pause, rewind, or wait around. Once it starts, React must finish it in one go so the DOM stays stable and consistent. 



**React’s render and commit phases form the core of how your UI *updates* - one phase *figures out* the changes, the other *executes* them. When you understand what happens in each stage, writing optimized, predictable, and maintainable React code stops being guesswork and starts becoming second nature.**




I’m still learning, so if I **missed something** or made a **mistake**, your contributions or feedback are more than welcome.  

Feel free to **explore, fork, or open issues** if you want something explained here. I’ll keep expanding this as I learn more.
