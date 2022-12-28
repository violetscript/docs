# Markup Expression

VioletScript supports markup similiar to XML, with the only exception of text nodes. The markup syntax can be used to initialize any user type. A container class must implement `INodeContainer.<T>`.

```
var c:Container = (
	<Container>
        <Item n=Infinity v={10**2} checked/>
    </Container>
);

// qualified tag name
<com.q.a.X/>;

// qualified tag name using colon
<s:Button/>;

var a:[Container] = <>
    <Container/>
    <!-- spread -->
    { [<Container/>,<Container/>,<Container/>] }
</>;
```