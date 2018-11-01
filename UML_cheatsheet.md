# UML Cheatsheet 
[UML Tutorial](http://plantuml.com/sequence-diagram)

## 1. UML overview:
```
@startuml

title
<font size = 30>VOD-Origin</font>
end title

participant Origin as O
participant ADS_VOD as V

O -> V: Test Body

@enduml
```
## 2. Participant:
- List of participant:
```
participant
actor
boundary
control
entity
database
```
- Example: [Participant](http://s.plantuml.com/imgw/sequence-diagram-qbbtnpuf.png)
```
participant Alice
participant "I have a really\nlong name" as L

actor Bob 
```

## 3. Escape character:
- we can escape the special character with **~**
```
~# This will escape the character "#"
```

## 4. Divider:
- We can divide the flow using divider: **== ==**
- Example: [divider](http://s.plantuml.com/imgw/sequence-diagram-os9lp785.png)
```
== Initialization ==
A -> B: test
== This is divider test ==
B <- A: test
```

## 5. Reference:
- Syntax:
```
1. Syntax 1: ref over A,B: Input line
2. Syntax 2: ref over A: Input line
3. Syntax 3: 
ref over A
	input body 1
	input body 2
end ref

ref over A,B
	input body 1
	input body 2
end ref
```
- Example: [ref](http://s.plantuml.com/imgw/sequence-diagram-xyxmeoje.png)
```
ref over Bob
  This can be on
  several lines
end ref
```

## 6. Note:
- Syntax:
```
1. Syntax 1: note left of A: input line
2. Syntax 2: note right of B: input line
3. Syntax 3: note over A,B: input line
4. Syntax 4: note over A: input line
5. Syntax 5: note left: input line
6. Syntax 6: note right: input line
7. Syntax 7: 
note over A
	input body 1
	input body 2
end note

note over A,B
	input body 1
	input body 2
end note

note left
	input body 1
	input body 2
end note
```
- Example: [note](http://s.plantuml.com/imgw/sequence-diagram-ccw9upb9.png)
```
    note left CMS: **CMS -> Ateme**

    note right of QC #aqua
        CDN Deploy
    end note
```


## 7. Group:
- many way to group message using the following keywords:
```
alt/else
opt
loop
par
break
critical
group, followed by a text to be displayed
```

### 7.1 alt/else
- Syntax:
```
alt display name of case
	case body

else other case
	case body

end
```
- Example: [alt/els](http://s.plantuml.com/imgw/sequence-diagram-fkaylnrn.png)
```
alt display name of case
	A -> B: test

else other case
	B -> A: test

end
```

### 7.2 group
- Syntax:
```
group Name of group
	Input Group Body 1
	Input Group body 2
end		
```
- Example: [group](http://s.plantuml.com/imgw/sequence-diagram-fkaylnrn.png)
```
group My own label
	Alice -> Log : Log attack start
    loop 1000 times
        Alice -> Bob: DNS Attack
    end
	Alice -> Log : Log attack end
end
```

## 8. Space:
- You can use **|||** to indicate some spacing in the diagram.
```
A -> B
|||
B -> A
```
- Example: [space](http://s.plantuml.com/imgw/sequence-diagram-bcre5f7h.png)

## 9. Line activate/deactivate
- The **activate** and **deactivate** are used to denote participant 
```
activate A
	A -> B: << createRequest >>
	activate B
		B -> A
	deactivate B
deactivate A
```
- Example: [activate/deactivate](http://s.plantuml.com/imgw/sequence-diagram-8vsdkqqg.png)

## 10. Direction arrow:
- Syntax:
```
A -> B	:	Normal 1 way arrow 
A -> A 	:	Normal self loop
-->		:	Dotline arrow
<->		: 	2 way arrow
->]		:	infinity arrow
o->		: 	arrow with 
```
- Example: [Direction arrow](http://s.plantuml.com/imgw/sequence-diagram-ymiek496.png)
			[Direction arrow 2](http://s.plantuml.com/imgw/sequence-diagram-d40ejet9.png)

## 11. Box around participant:
- Syntax:
```
box "Internal Service" #LightBlue
	participant Bob
	participant Alice
end box
```
- Example: [box around participant](http://s.plantuml.com/imgw/sequence-diagram-opkitaai.png)
```
box "Internal Service" #LightBlue
	participant Bob
	participant Alice
end box
participant Other

Bob -> Alice : hello
```

## 12. Format
- Syntax:
```
  This is **bold**
  This is //italics//
  This is ""monospaced""
  This is --stroked--
  This is __underlined__
  This is ~~waved~~
  This is <u:red> Underline with red </u>
  This is <b> This is bolding all in the html tag </b>
  This is <color #118888> color the word with color code </color>
```
- Example: [Format](http://s.plantuml.com/imgw/sequence-diagram-40y257ai.png)

