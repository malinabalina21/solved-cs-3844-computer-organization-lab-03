Download Link: https://assignmentchef.com/product/solved-cs-3844-computer-organization-lab-03
<br>
<strong>  </strong>




This lab continues introducing you to the x86 Intel instruction set. Set up a new project in Visual Studio using the Lab3.cpp file. Create an Empty Windows Console application and “Add Existing” to make Lab3.cpp part of the project. In fact, you can reuse Lab2 as long as you rename the main from Lab #2.




Also we can disable address space randomization byte going to project properties and disabling it. This should make everyone’s EIP the same.










Once you have the project compiled, go ahead and run it and observe what it does. Now, set breakpoints at the two “No Operation” (nop) instructions. Run the program in the Visual Studio debugger and set up the memory/register windows as before. You can also go to DebugWindowsDisassembly if you wish to see the disassembled code intermixed with the C code.




<ol>

 <li>What is the value of EIP? (It could still vary due to different compiler optimizations.) Whatever it is, it should be the same every time you re-run the program.</li>

</ol>







<ol start="2">

 <li>In the memory window, type gString and press enter. See the hexadecimal values for the ASCII characters?</li>

</ol>




<ol>

 <li>What is the hex value of a lowercase ‘o’?</li>

</ol>




<ol>

 <li>What is the address of gString? (May vary)</li>

</ol>




<ol>

 <li>Compare the address of gString with esp. What is the difference in values? (Use a calculator and subtract.) Are they close? Why or why not?</li>

</ol>




<ol>

 <li>What is the address of localString? (May vary)</li>

</ol>







<ol>

 <li>Is it close in value to esp? Yes, it is! Why is that?</li>

 <li>Type gString in the memory window again. Click “step into” until the yellow arrow is pointing at the “lea edx,gString” instruction. Before looking, take a guess at the value of edx. What is the value of edx?</li>

</ol>




<ol>

 <li>Where does that number come from?</li>

</ol>




<ol>

 <li>Why is the order of the hex digits in edx backwards from that in memory?</li>

</ol>




<ol>

 <li>Step to the next instruction inside SEARCH_LOOP. Look up the instruction you just executed (lea) to get an idea of what it does. What is in edx now? Put edx in the memory window, what do you see?</li>

</ol>




<ol start="3">

 <li>Step through the following code until you understand what it does. Then comment each line such that a novice computer person would be able to read and understand too. Stop when you get to SEARCH_LOOP2.</li>

</ol>




mov al, byte ptr [edx] ____________________________________________________







cmp al,0                Ex: BAD “check al for zero” GOOD: Check string for NULL




je EXIT_LOOP          ____________________________________________________ inc edx              _________________________________________







cmp al,’i’             _____________________________________________________




jne SEARCH_LOOP       _____________________________________________________







dec edx                _____________________________________________________







mov byte ptr [edx],’e’ _____________________________________________________







<ol start="4">

 <li>Briefly describe the overall function of that piece of code. Look up any instructions that you don’t know. You can Google something like “x86 intel dec” for example.</li>

</ol>




<ol start="5">

 <li>Inside SEARCH_LOOP2 you see the instruction “cmp byte ptr [edx],0.” In a few sentences, describe what that instruction is doing. Don’t just say, “It’s comparing something to zero,” but rather dig a little deeper. Consider how it accomplishes a comparison and why there is a “je” (jump if equal, i.e. jump if the zero flag is set to one) after it.</li>

</ol>




<ol start="6">

 <li>In the code you see the “byte ptr” notation – what do you think that does? If you changed it to WORD PTR, what register would you use in place of AL? And the same question for a DWORD PTR.</li>

</ol>




<ol start="7">

 <li>Briefly describe what the COPY_LOOP does. Step through the loop and determine under what conditions the jne doesn’t loop back.</li>

</ol>