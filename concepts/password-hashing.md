<h1>Why password hashing?</h1>
<p>
Sensitive information (eg. passwords) should not be stored as plain text in case an unauthorized person accesses the database. Storing passwords as hashed values instead of plain text enhances their security storage.
</p>

<p>
<h1>What is password hashing?</h1>
<li>A hash is a mathematical function that takes an input (in this case, a password) and produces a fixed-size string of characters, which is typically a combination of letters and numbers. </li>
<li>The hash value or hash code, is unique to the input. </li>
<li>Hash functions are designed to be one-way, meaning that it is computationally infeasible to reverse-engineer the original input from the hash value. </li>
</p>

<h1>What is the difference between hashing and encryption?</h1>
<p>
<li>Hashing is a one-way function, while encryption is a two-way function.
<ul><li>One-way function means it is not possible to compute the original input from the hash value via reverse-engineering. - Best suited for storing passwords.</li></ul>
<ul><li>A two-way function that allows the retrieval of the original value from the encrypted value. - Best suited for storing emails and other PII (personal identifiable information)</li></ul>
</li>
</p>

<h1>If hashing is a one-way function, how do we verify user credentials?</h1>
<p>
A hash of the user's plain text password is created when the user enters his/her password and then the new hashed value is compared to the hash value stored in the database. If the hashes match, the password is correct. The beauty of hashing is that we never need to know a user's actual password.

A hacker may use brute force attacks (using different combinations of passwords) or, has access to a list passwords from the user's hacked accounts to try to generate password that matches the hash od the original password. While this will require high-speed resources or high computation power, these methods have been proven to be successful for older hashing algorithms, like the SHA1 family, given the computing power currently available. Therefore, it is immensely important to use newer hashing algorithms and other best practices to ensure that the generated hash is impossible to crack — or would take several decades of permutation/combination to crack.
</p>

<h1>What is salting?</h1>
<p>
<li> A salt value is a randomly generated value (usually random binary data such as random bytes of data) that is added to the password when creating a hash. Each password has its own unique salt.</li>
<li>The length of the salt depends on the hashing algorithm used. In newer algorithms, the salt is generated automatically, eliminating the need to provide one. </li>
</p>
