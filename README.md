jsoup xssfilter
========

jsoup 라이브러리의 org.jsoup.safety.Whitelist 를 xml 로 관리하는 라이브러리

# Install

### maven

```
maven clean package
```

# Usage

### default configuration

```java
String dirty = "<script>alert('attack!!');</script>";
String clean = XssFilter.getInstance().doFilter(dirty);
```

### custom configuration

```java
String dirty = "<b onmouseover=alert('Wufff!')>click me!</b>";
String clean = XssFilter.getInstance("other-config.xml").doFilter(dirty);
```

# xml configuration

### default

```xml
<whitelistRule>
	<attributeGroups>
		<attrGroup name="Core">
			<attr>id</attr>
			<attr>class</attr>
			<attr>title</attr>
			<attr>style</attr>
		</attrGroup>
		<attrGroup name="I18n">
			<attr>lang</attr>
			<attr>dir</attr>
		</attrGroup>
		<attrGroup name="Cellhalign">
			<attr>align</attr>
			<attr>char</attr>
			<attr>charoff</attr>
		</attrGroup>
		<attrGroup name="Cellvalign">
			<attr>valign</attr>
		</attrGroup>
		<attrGroup name="Attrs">
			<attr>id</attr>
			<attr>class</attr>
			<attr>title</attr>
			<attr>style</attr>
			<attr>lang</attr>
			<attr>dir</attr>
		</attrGroup>
	</attributeGroups>
	<tags>
		<tag name="a">
			<attr name="Attrs" />
			<attr name="charset" />
			<attr name="type" />
			<attr name="name" />
			<attr name="href">
				<protocol>http</protocol>
				<protocol>https</protocol>
				<protocol>ftp</protocol>
				<protocol>mailto</protocol>
			</attr>
			<attr name="hreflang" />
			<attr name="rel" />
			<attr name="rev" />
			<attr name="shape" />
			<attr name="coords" />
			<attr name="tabindex" />
		</tag>
		<tag name="abbr">
			<attr name="Attrs" />
		</tag>
		<tag name="acronym">
			<attr name="Attrs" />
		</tag>
		<tag name="address">
			<attr name="Attrs" />
		</tag>
		<tag name="area">
			<attr name="Attrs" />
			<attr name="shape" />
			<attr name="coords" />
			<attr name="href">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="nohref" />
			<attr name="alt" />
			<attr name="tabindex" />
		</tag>
		<tag name="b">
			<attr name="Attrs" />
		</tag>
		<tag name="base">
			<attr name="href">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="target" />
		</tag>
		<tag name="basefont">
			<attr name="Attrs" />
			<attr name="size" />
			<attr name="color" />
			<attr name="face" />
		</tag>
		<tag name="bdo">
			<attr name="Attrs" />
			<attr name="dir" />
		</tag>
		<tag name="big">
			<attr name="Attrs" />
		</tag>
		<tag name="blockquote">
			<attr name="Attrs" />
			<attr name="cite">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
		</tag>
		<tag name="br">
			<attr name="Core" />
			<attr name="clear" />
		</tag>
		<tag name="button">
			<attr name="Attrs" />
			<attr name="name" />
			<attr name="value" />
			<attr name="type" />
			<attr name="disabled" />
			<attr name="tabindex" />
		</tag>
		<tag name="caption">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="center">
			<attr name="Attrs" />
		</tag>
		<tag name="cite">
			<attr name="Attrs" />
			<attr name="cite">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
		</tag>
		<tag name="code">
			<attr name="Attrs" />
		</tag>
		<tag name="col">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
			<attr name="span" />
			<attr name="width" />
		</tag>
		<tag name="colgroup">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
			<attr name="span" />
			<attr name="width" />
		</tag>
		<tag name="dd">
			<attr name="Attrs" />
		</tag>
		<tag name="del">
			<attr name="Attrs" />
			<attr name="cite">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="datetime" />
		</tag>
		<tag name="dfn">
			<attr name="Attrs" />
		</tag>
		<tag name="dir">
			<attr name="Attrs" />
			<attr name="compact" />
		</tag>
		<tag name="div">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="dl">
			<attr name="Attrs" />
			<attr name="compact" />
		</tag>
		<tag name="dt">
			<attr name="Attrs" />
		</tag>
		<tag name="em">
			<attr name="Attrs" />
		</tag>
		<tag name="fieldset">
			<attr name="Attrs" />
		</tag>
		<tag name="font">
			<attr name="Attrs" />
			<attr name="size" />
			<attr name="face" />
			<attr name="color" />
		</tag>
		<tag name="h1">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="h2">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="h3">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="h4">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="h5">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="h6">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="hr">
			<attr name="Attrs" />
			<attr name="align" />
			<attr name="noshade" />
			<attr name="size" />
			<attr name="width" />
		</tag>
		<tag name="i">
			<attr name="Attrs" />
		</tag>
		<tag name="img">
			<attr name="Attrs" />
			<attr name="src">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="alt" />
			<attr name="longdesc" />
			<attr name="name" />
			<attr name="height" />
			<attr name="width" />
			<attr name="usemap" />
			<attr name="ismap" />
		</tag>
		<tag name="input">
			<attr name="Attrs" />
			<attr name="type" />
			<attr name="name" />
			<attr name="value" />
			<attr name="checked" />
			<attr name="disabled" />
			<attr name="readonly" />
			<attr name="size" />
			<attr name="maxlength" />
			<attr name="src" />
			<attr name="alt" />
			<attr name="usemap" />
			<attr name="ismap" />
			<attr name="tabindex" />
			<attr name="accept" />
		</tag>
		<tag name="ins">
			<attr name="Attrs" />
			<attr name="cite">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="datetime" />
		</tag>
		<tag name="isindex">
			<attr name="Attrs" />
			<attr name="prompt" />
		</tag>
		<tag name="kbd">
			<attr name="Attrs" />
		</tag>
		<tag name="label">
			<attr name="Attrs" />
			<attr name="for" />
		</tag>
		<tag name="legend">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="li">
			<attr name="Attrs" />
			<attr name="type" />
			<attr name="value" />
			<attr name="compact" />
		</tag>
		<tag name="main">
			<attr name="Attrs" />
		</tag>
		<tag name="map">
			<attr name="Attrs" />
			<attr name="name" />
		</tag>
		<tag name="marquee">
			<attr name="Attrs" />
			<attr name="disabled" />
			<attr name="tabindex" />
			<attr name="title" />
			<attr name="behavior" />
			<attr name="bgcolor" />
			<attr name="direction" />
			<attr name="height" />
			<attr name="hspace" />
			<attr name="loop" />
			<attr name="scrollamount" />
			<attr name="scrolldelay" />
			<attr name="width" />
		</tag>
		<tag name="menu">
			<attr name="Attrs" />
			<attr name="compact" />
		</tag>
		<tag name="nobr">
			<attr name="disabled" />
			<attr name="tabindex" />
			<attr name="title" />
		</tag>
		<tag name="ol">
			<attr name="Attrs" />
			<attr name="type" />
			<attr name="reversed" />
			<attr name="start" />
			<attr name="compact" />
		</tag>
		<tag name="optgroup">
			<attr name="Attrs" />
			<attr name="disabled" />
			<attr name="label" />
		</tag>
		<tag name="option">
			<attr name="Attrs" />
			<attr name="selected" />
			<attr name="disabled" />
			<attr name="label" />
			<attr name="value" />
		</tag>
		<tag name="p">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="param">
			<attr name="id" />
			<attr name="name" />
			<attr name="type" />
			<attr name="value" />
			<attr name="valuetype" />
		</tag>
		<tag name="pre">
			<attr name="Attrs" />
			<attr name="width" />
		</tag>
		<tag name="q">
			<attr name="Attrs" />
			<attr name="cite">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
		</tag>
		<tag name="rt">
			<attr name="Attrs" />
			<attr name="name" />
			<attr name="rbspan" />
		</tag>
		<tag name="ruby">
			<attr name="Attrs" />
			<attr name="name" />
		</tag>
		<tag name="s">
			<attr name="Attrs" />
		</tag>
		<tag name="samp">
			<attr name="Attrs" />
		</tag>
		<tag name="select">
			<attr name="Attrs" />
			<attr name="name" />
			<attr name="size" />
			<attr name="multiple" />
			<attr name="disabled" />
			<attr name="tabindex" />
		</tag>
		<tag name="small">
			<attr name="Attrs" />
		</tag>
		<tag name="span">
			<attr name="Attrs" />
			<attr name="align" />
		</tag>
		<tag name="strike">
			<attr name="Attrs" />
		</tag>
		<tag name="strong">
			<attr name="Attrs" />
		</tag>
		<tag name="sub">
			<attr name="Attrs" />
		</tag>
		<tag name="sup">
			<attr name="Attrs" />
		</tag>
		<tag name="table">
			<attr name="Attrs" />
			<attr name="border" />
			<attr name="cellpadding" />
			<attr name="cellspacing" />
			<attr name="frame" />
			<attr name="rules" />
			<attr name="summary" />
			<attr name="width" />
			<attr name="bgcolor" />
		</tag>
		<tag name="tbody">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
		</tag>
		<tag name="td">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
			<attr name="abbr" />
			<attr name="axis" />
			<attr name="headers" />
			<attr name="scope" />
			<attr name="rowspan" />
			<attr name="colspan" />
			<attr name="bgcolor" />
		</tag>
		<tag name="textarea">
			<attr name="Attrs" />
			<attr name="name" />
			<attr name="rows" />
			<attr name="cols" />
			<attr name="disabled" />
			<attr name="readonly" />
			<attr name="tabindex" />
		</tag>
		<tag name="tfoot">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
		</tag>
		<tag name="th">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
			<attr name="abbr" />
			<attr name="axis" />
			<attr name="headers" />
			<attr name="scope" />
			<attr name="rowspan" />
			<attr name="colspan" />
			<attr name="bgcolor" />
		</tag>
		<tag name="thead">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
		</tag>
		<tag name="tr">
			<attr name="Attrs" />
			<attr name="Cellhalign" />
			<attr name="Cellvalign" />
			<attr name="bgcolor" />
		</tag>
		<tag name="tt">
			<attr name="Attrs" />
		</tag>
		<tag name="u">
			<attr name="Attrs" />
		</tag>
		<tag name="ul">
			<attr name="Attrs" />
			<attr name="compact" />
			<attr name="type" />
		</tag>
		<tag name="var">
			<attr name="Attrs" />
		</tag>
		<tag name="wbr" />
		<tag name="xml">
			<attr name="Core" />
		</tag>
		<tag name="xmp">
			<attr name="Core" />
			<attr name="align" />
		</tag>
		<!-- html5 -->
		<tag name="article">
			<attr name="Attrs" />
		</tag>
		<tag name="aside">
			<attr name="Attrs" />
		</tag>
		<tag name="audio">
			<attr name="Attrs" />
			<attr name="controls" />
		</tag>
		<tag name="bdi">
			<attr name="Attrs" />
		</tag>
		<tag name="canvas">
			<attr name="Attrs" />
			<attr name="height" />
			<attr name="width" />
		</tag>
		<tag name="command">
			<attr name="Attrs" />
		</tag>
		<tag name="data">
			<attr name="Attrs" />
		</tag>
		<tag name="datalist">
			<attr name="Attrs" />
		</tag>
		<tag name="details">
			<attr name="Attrs" />
			<attr name="open" />
		</tag>
		<tag name="figcaption">
			<attr name="Attrs" />
		</tag>
		<tag name="figure">
			<attr name="Attrs" />
		</tag>
		<tag name="footer">
			<attr name="Attrs" />
		</tag>
		<tag name="header">
			<attr name="Attrs" />
		</tag>
		<tag name="keygen">
			<attr name="Attrs" />
		</tag>
		<tag name="mark">
			<attr name="Attrs" />
		</tag>
		<tag name="meter">
			<attr name="Attrs" />
			<attr name="form" />
			<attr name="high" />
			<attr name="low" />
			<attr name="max" />
			<attr name="min" />
			<attr name="optimum" />
			<attr name="value" />
		</tag>
		<tag name="nav">
			<attr name="Attrs" />
		</tag>
		<tag name="output">
			<attr name="Attrs" />
			<attr name="for" />
			<attr name="form" />
			<attr name="name" />
		</tag>
		<tag name="progress">
			<attr name="Attrs" />
			<attr name="max" />
			<attr name="value" />
		</tag>
		<tag name="rp">
			<attr name="Attrs" />
		</tag>
		<tag name="section">
			<attr name="Attrs" />
		</tag>
		<tag name="source">
			<attr name="Attrs" />
			<attr name="src">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="type" />
		</tag>
		<tag name="summary">
			<attr name="Attrs" />
		</tag>
		<tag name="time">
			<attr name="Attrs" />
			<attr name="datetime" />
		</tag>
		<tag name="track">
			<attr name="Attrs" />
			<attr name="default" />
			<attr name="kind" />
			<attr name="label" />
			<attr name="src">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="srclang" />
		</tag>
		<tag name="video">
			<attr name="Attrs" />
			<attr name="controls" />
			<attr name="height" />
			<attr name="width" />
			<attr name="src">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="poster">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
		</tag>
		<!-- dangerous -->
		<tag name="title" disabled="true">
			<attr name="I18n" />
		</tag>
		<tag name="applet" disabled="true">
			<attr name="Attrs" />
			<attr name="codebase" />
			<attr name="archive" />
			<attr name="code" />
			<attr name="object" />
			<attr name="alt" />
			<attr name="name" />
			<attr name="width" />
			<attr name="height" />
			<attr name="align" />
			<attr name="hspace" />
			<attr name="vspace" />
		</tag>
		<tag name="script" disabled="true">
			<attr name="charset" />
			<attr name="defer" />
			<attr name="src" />
			<attr name="type" />
		</tag>
		<tag name="noframes" disabled="true">
			<attr name="Attrs" />
		</tag>
		<tag name="noscript" disabled="true">
			<attr name="Attrs" />
		</tag>
		<tag name="link" disabled="true">
			<attr name="Attrs" />
			<attr name="charset" />
			<attr name="href">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="hreflang" />
			<attr name="type" />
			<attr name="rel" />
			<attr name="rev" />
			<attr name="media" />
		</tag>
		<tag name="object" disabled="true">
			<attr name="Attrs" />
			<attr name="archive" />
			<attr name="classid" />
			<attr name="codebase" />
			<attr name="codetype" />
			<attr name="data" />
			<attr name="declare" />
			<attr name="standby" />
			<attr name="tabindex" />
			<attr name="type" />
			<attr name="width" />
			<attr name="usemap" />
		</tag>
		<tag name="embed" disabled="true">
			<attr name="Attrs" />
			<attr name="align" />
			<attr name="disabled" />
			<attr name="height" />
			<attr name="hidden" />
			<attr name="hspace" />
			<attr name="name" />
			<attr name="pluginspage" />
			<attr name="src">
				<protocol>http</protocol>
				<protocol>https</protocol>
			</attr>
			<attr name="type" />
			<attr name="width" />
			<attr name="units" />
		</tag>
		<tag name="form" disabled="true">
			<attr name="Attrs" />
			<attr name="action" />
			<attr name="method" />
			<attr name="enctype" />
			<attr name="accept" />
			<attr name="name" />
			<attr name="accept-charset" />
		</tag>
		<tag name="frame" disabled="true">
			<attr name="Attrs" />
			<attr name="longdesc" />
			<attr name="name" />
			<attr name="src" />
			<attr name="frameborder" />
			<attr name="marginwidth" />
			<attr name="marginheight" />
			<attr name="noresize" />
			<attr name="scrolling" />
		</tag>
		<tag name="frameset" disabled="true">
			<attr name="Attrs" />
			<attr name="cols" />
			<attr name="rows" />
		</tag>
		<tag name="iframe" disabled="true">
			<attr name="Core" />
			<attr name="longdesc" />
			<attr name="name" />
			<attr name="src" />
			<attr name="frameborder" />
			<attr name="marginwidth" />
			<attr name="marginheight" />
			<attr name="scrolling" />
			<attr name="align" />
			<attr name="height" />
			<attr name="width" />
		</tag>
		<tag name="body" disabled="true">
			<attr name="Attrs" />
			<attr name="background" />
			<attr name="text" />
			<attr name="link" />
			<attr name="vlink" />
			<attr name="alink" />
			<attr name="bgcolor" />
		</tag>
		<tag name="html" disabled="true">
			<attr name="I18n" />
			<attr name="version" />
		</tag>
		<tag name="meta" disabled="true">
			<attr name="I18n" />
			<attr name="content" />
			<attr name="http-equiv" enforced="nofollow" />
			<attr name="name" />
			<attr name="scheme" />
		</tag>
		<tag name="style" disabled="true">
			<attr name="I18n" />
			<attr name="type" />
			<attr name="media" />
			<attr name="title" />
		</tag>
	</tags>
</whitelistRule>
```

# roadmap

1. StAX 방식의 파서 지원
2. 어트리뷰트 그룹(attributeGroups) 의 멀티 depth
3. whitelist domain 지원
4. 태그 내부의 허용가능 태그 지원
