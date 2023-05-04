Download Link: https://assignmentchef.com/product/solved-csci-3104-problem-set-10
<br>
<ol>

 <li>(15 pts total) A <em>matching </em>in a graph <em>G </em>is a subset <em>E<sub>M </sub></em>⊆ <em>E</em>(<em>G</em>) of edges such that each vertex touches at most one of the edges in <em>E<sub>M</sub></em>. Recall that a bipartite graph is a graph <em>G </em>on two sets of vertices, <em>V</em><sub>1 </sub>and <em>V</em><sub>2</sub>, such that every edge has one endpoint in <em>V</em><sub>1 </sub>and one endpoint in <em>V</em><sub>2</sub>. We sometimes write <em>G </em>= (<em>V</em><sub>1</sub><em>,V</em><sub>2</sub>;<em>E</em>) for this situation. For example:</li>

</ol>

<em>V</em><sub>1 </sub>:          1          2          3           4            5           6

<em>V</em><sub>2 </sub>:          7          8          9         10          11

The edges in the above example consist of all the lines, whether solid or dotted; the solid lines form a matching.

The <em>bipartite maximum matching </em>problem is to find a matching in a given bipartite graph <em>G </em>, which has the maximum number of edges among all matchings in <em>G</em>.

<ul>

 <li>Prove that a maximum matching in a bipartite graph <em>G </em>= (<em>V</em><sub>1</sub><em>,V</em><sub>2</sub>;<em>E</em>) has size at most min{|<em>V</em><sub>1</sub>|<em>,</em>|<em>V</em><sub>2</sub>|}.</li>

 <li>Show how you can use an algorithm for max-flow to solve bipartite maximummatching on undirected simple bipartite graphs. That is, give an algorithm which, given an undirected simple bipartite graph <em>G </em>= (<em>V</em><sub>1</sub><em>,V</em><sub>2</sub>;<em>E</em>), (1) constructs a directed, weighted graph <em>G</em><sup>0 </sup>(which need not be bipartite) with weights <em>w </em>: <em>E</em>(<em>G</em><sup>0</sup>) → R as well as two vertices <em>s,t </em>∈ <em>V </em>(<em>G</em><sup>0</sup>), (2) solves max-flow for (<em>G</em><sup>0</sup><em>,w</em>)<em>,s,t</em>, and (3) uses the solution for max-flow to find the maximum matching in <em>G</em>. Your algorithm may use any max-flow algorithm as a subroutine.</li>

 <li>Show the weighted graph constructed by your algorithm on the example bipartitegraph above.</li>

</ul>

<ol start="2">

 <li>(20 pts total) In the review session for his Deep Wizarding class, Dumbledore reminds everyone that the logical definition of NP requires that the number of <em>bits </em>in the witness <em>w </em>is polynomial in the number of bits of the input <em>n</em>. That is, |<em>w</em>| = <em>poly</em>(<em>n</em>). With a smile, he says that in beginner wizarding, witnesses are usually only logarithmic in size, i.e., |<em>w</em>| = <em>O</em>(log<em>n</em>).

  <ul>

   <li>Because you are a model student, Dumbledore asks you to prove, in front of thewhole class, that any such property is in the complexity class P.</li>

   <li>Well done, Dumbledore says. Now, explain why the logical definition of NP impliesthat any problem in NP can be solved by an exponential-time algorithm.</li>

  </ul></li>

</ol>

1

<ul>

 <li>Dumbledore then asks the class: “So, is NP a good formalization of the notion ofproblems that can be solved by brute force? Discuss.” Give arguments for both possible answers.</li>

</ul>

<ol start="3">

 <li>(30 pts total) The Order of the Phoenix is trying to arrange to watch all the corridors in Hogwarts, to look out for any Death Eaters. Professor McGonnagall has developed a new spell, Multi-Directional Sight, which allows a person to get a 360-degree view of where they are currently standing. Thus, if they are able to place a member of the Order at every <em>intersection </em>of hallways, they’ll be able to monitor all hallways. In order not to spare any personnel, they want to place as few people as possible at intersections, while still being able to monitor every hallway. (And they really need to monitor <em>every </em>hallway, since Death Eaters could use Apparition to teleport into an arbitrary hallway in the middle of the school.) Call a subset <em>S </em>of intersections “safe,” if, by placing a member of the Order at each intersection in <em>S</em>, every hallway is watched.

  <ul>

   <li>Formulate the above as an optimization problem on a graph. Argue that yourformulation is an accurate reflection of the problem. In your formulation, show that the following problem is in NP: Given a graph <em>G </em>and an integer <em>k</em>, decide whether there a safe subset of size ≤ <em>k</em>.</li>

   <li>Consider the following greedy algorithm to find a safe subset</li>

  </ul></li>

</ol>

S = empty mark all hallways unwatched while there is an unwatched intersection pick any unwatched hallway; let u,v be its endpoints add u to S for all hallways h with u as one of its endpoints mark h watched

end

end

Although this algorithm need not find the minimum number of people needed to cover all hallways, prove that it always outputs a safe set, and prove that it always runs in polynomial time.

<ul>

 <li>Note that, in order to be polynomial-time, an algorithm for this problem cannotsimply try all possible subsets of intersections. Prove why not.</li>

 <li>Give an example where the algorithm from (3b) outputs a safe set that is strictlylarger than the smallest one. In other words, give a graph <em>G</em>, give a list of vertices</li>

</ul>

in the order in which they are picked by the algorithm, and a safe set in <em>G </em>which is strictly smaller than the safe set output by the algorithm.

<ul>

 <li>Consider the following algorithm:</li>

</ul>

S = empty mark all hallways unwatched while there is an unwatched hallway pick any unwatched hallway; let u,v be its endpoints add u,v to S for all hallways h with u or v one of their endpoints mark h watched

end

end

Prove that this algorithm always returns a safe set, and runs in polynomial time.

<ul>

 <li>In any safe set of intersections, each hallway is watched by <em>at least </em>one member of the Order. Use this to show that the algorithm from (3e) always outputs a safe set whose size is no more than twice the size of the smallest safe set. Note: you don’t need to know what the smallest safe set is to prove this! All you need is the fact stated here.</li>

</ul>

This is called a “2-approximation algorithm,” because it is guaranteed to output a solution that is no worse than a factor of 2 times an optimal solution.

<ul>

 <li>Does the algorithm from (3b) always produce a safe set no bigger than that produced by the algorithm in (3e)? If so, give a proof; if not, give a counterexample. A counterexample here consists of a graph, and for each algorithm, the list of vertices it chooses in the order it chooses them, such that the safe set output by algorithm (3b) is at least as large as the safe set output by algorithm (3e). If you are unable to give either a proof or a counterexample, then for partial credit give a plausible intuitive argument for your answer.</li>

 <li>Compare the greedy algorithm from (3e) with the greedy algorithm from (3b). Show which runs faster asymptotically? Which of these two algorithms would you rather use to solve the Order of the Phoenix’s problem and why?</li>

 <li>This problem is, in fact, NP-complete. Why does the 2-approximation polynomialtime algorithm from (3e) <em>not </em>show that P=NP?<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a></li>

</ul>

<ol start="4">

 <li>(20 pts extra credit) Every young wizard learns the classic NP-complete problem of determining whether some unweighted, undirected graph <em>G </em>= (<em>V,E</em>) contains a simple path of length at least <em>k </em>(where both <em>G </em>and <em>k </em>are part of the input to the problem), known as the Longest Path Problem. Recall that a <em>simple path </em>is a path (<em>v</em><sub>1</sub><em>,v</em><sub>2</sub><em>,…,v<sub>`</sub></em>) where each (<em>v<sub>i</sub>,v<sub>i</sub></em><sub>+1</sub>) in the path is an edge, and all the <em>v<sub>i </sub></em>are distinct; its length is <em>` </em>− 1 (=the number of edges in the path).

  <ul>

   <li>Ginny Weasley is working on a particularly tricky instance of this problem forher Witchcraft and Algorithms class, and she believes she has written down a “witness” for a particular input (<em>G,k</em>) in the form of a path <em>P </em>on its vertices. Explain how she should verify in polynomial time whether <em>P </em>is or is not simple path of length ≥ <em>k</em>. (And hence, demonstrate that the problem of Longest Path is in the complexity class NP.)</li>

   <li>For the final exam in Ginny’s class, each student must visit the Oracle’s Well inthe Forbidden Forest. For every bronze Knut a young wizard tosses into the Well, the Oracle will give a yes or no response as to whether, given an arbitrary graph <em>G </em>and an integer <em>k</em>, <em>G </em>contains a simple path of length ≥ <em>k</em>. Ginny is given an arbitrary graph <em>G </em>and must find the longest simple path in <em>G</em>.</li>

  </ul></li>

</ol>

First, she realizes it would be useful to determine the <em>length </em>of the longest simple path. Describe an algorithm that will allow Ginny to use the Oracle to find <em>the length </em>of the longest simple path in <em>G </em>by asking it a series of questions, each involving a modified version of the original graph <em>G </em>and a number <em>k</em>. Her solution must not cost more Knuts than a number that grows polynomially as a function of the number of vertices in <em>G</em>. (Hence, prove that if we can solve the Longest Path <em>decision </em>problem in polynomial time, we can solve its <em>optimization </em>problem as well.)

<ul>

 <li>Next, once she knows the length <em>` </em>of the longest simple path in <em>G</em>, Ginny muse use the Oracle to actually find a path of length <em>`</em>. Describe an algorithm that will allow Ginny to use the Oracle to find the longest simple path in <em>G </em>by asking it a series of questions, each involving a modified version of the original graph <em>G </em>and a number <em>k </em>of her choosing (for each question she can ask about a different graph <em>G </em>and a different number <em>k</em>). Her solution must not cost more Knuts than a number that grows polynomially as a function of the number of vertices in <em>G</em>. (Hence,</li>

</ul>

it would follow that P=NP, but this assumption remains a conjecture, and opinion in the research community is divided on whether this conjecture is true or false. We will provide references to these results after the problem set has been handed in.

prove that if we can solve the Longest Path <em>decision </em>problem in polynomial time, we can solve its <em>search </em>problem as well.)

<ol start="5">

 <li>(20 pts extra credit) Recall that the <em>MergeSort </em>algorithm (Chapter 2.3 of CLRS) is a sorting algorithm that takes Θ(<em>n</em>log<em>n</em>) time and Θ(<em>n</em>) space. In this problem, you will implement and instrument MergeSort, then perform a numerical experiment that verifies this asymptotic analysis. There are two functions and one experiment to do this.

  <ul>

   <li>MergeSort(A,n) takes as input an unordered array <em>A</em>, of length <em>n</em>, and returns both an in-place sorted version of <em>A </em>and a count <em>t </em>of the number of atomic operations performed by MergeSort.</li>

   <li>randomArray(n) takes as input an integer <em>n </em>and returns an array <em>A </em>such that for each 0 ≤ <em>i &lt; n</em>, <em>A</em>[<em>i</em>] is a uniformly random integer between 1 and <em>n</em>. (It is okay if <em>A </em>is a random permutation of the first <em>n </em>positive integers; see the end of Chapter 5.3.)</li>

   <li>From scratch, implement the functions MergeSort and randomArray. You may not use any library functions that make their implementation trivial. You may use a library function that implements a pseudorandom number generator in order to implement randomArray.</li>

  </ul></li>

</ol>

Submit a paragraph that explains how you instrumented MergeSort, i.e., explain which operations you counted and why these are the correct ones to count.

<ul>

 <li>For each of , run MergeSort(randomArray(n),n) fives times and record the tuple (<em>n,</em>h<em>t</em>i), where h<em>t</em>i is the average number of operations your function counted over the five repetitions. Use whatever software you like to make a line plot of these 24 data points; overlay on your data a function of the form <em>T</em>(<em>n</em>) = <em>An</em>log<em>n</em>, where you choose the constant <em>A </em>so that the function is close to your data.</li>

</ul>

Hint 1: To increase the aesthetics, use a log-log plot.

Hint 2: Make sure that your <em>MergeSort </em>implementation uses only two arrays of length <em>n </em>to do its work. (For instance, don’t do recursion with pass-by-value.)

<a href="#_ftnref1" name="_ftn1">[1]</a> Interestingly, it is known that if there were a 1.3606…-approximation algorithm for this problem in polynomial time, then it would follow that P=NP, but that is a very nontrivial theorem. Under a standard complexity-theoretic assumption, even if there were a 1.99999-approximation algorithm in polynomial time,