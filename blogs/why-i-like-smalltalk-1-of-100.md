# Why I like Smalltalk: Part 1 of 100 - Documentation

## Smalltalk Documentation follows CRC(Class, Responsibilities & Collaborators)
- For those who don't know what CRC is, it's a tool that helps design objects. 
- A CRC card consists of Class name at the top, responsibilities on the left side & collaborators on the right.
- Since a card models only one object, it enables rapid prototyping. It is feasible to go through many iterations before settling on an implementation.
- ![A sample CRC card](/images/crc-example.gif)


## Smalltalk Documentation talks to you
I noticed this in Pharo's documentation. 
Classes have comments as they talk to you. They give you an overview of what they are and what they can do. They also tell you how you get started with them with some examples.

### Example from Pharo's documentation for `Point`
    I represent an x,y pair of numbers usually designating a location on the screen.

    My instances are created either using the message `@` or `x:y:` or `r:degrees:` as follows:

    ```
    | pt |
    pt := 10@20.
    pt x 
    >>> 10
    pt y
    >>> 20 			 
    ```

    ```
    | pt |
    pt := Point x: 10 y: 20.
    pt x 
    > 10
    pt y
    > 20 			 
    ```

    I define many nice messages that deal with point such as: 
    - arithmetic such as \+, \*, reciprocal, min, abs,
    - comparison \<, \<=, \=, \>, \>=, closeTo: 
    - geometry such as sideOf:, to:intersects:to:, 
    - polar coordinates,
    - extent such as scaleTo:
    - transformation such as negated, translatedBy:, scaleBy:
    - rounding with roundTo:, roundUpTo:, truncateTo:, truncated

How cool is that? That makes me wanna take Point for a coffee.
I have adopted this style of documentation for just about everything. 

## Inbuilt support for documentation
The Smalltalk IDE's are one of the most mature IDEs I have ever used. They have inbuilt support for documentation along with the class. Although this might be more of an IDE feature, it has been since the beginning(probably).

![Documentation in Pharo](/images/documentation-in-pharo.png)
