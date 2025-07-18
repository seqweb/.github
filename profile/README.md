## ***SeqWeb*** _is to the_ **OEIS** _as_ **DBpedia** _is to_ **Wikipedia**.

This terse framing analogy can be useful for "quadrangulating" on the goals and substance of the SeqWeb project.  

All four components of the analogy are web resources addressible via Internet domains: `seqweb.org`, `oeis.org`, `dbpedia.org` and `wikipedia.org` respectively.

These four web entities can be organized natually along two axes: _subject focus_ and _content type_. 

- The _subject focus_ of both Wikipedia and DBpedia is general information, while for both the OEIS and SeqWeb it is the specialized area of mathematical integer sequences.

- Along the _content type_ dimension both Wikipedia and the OEIS present rich web pages of interlinked documents intended for human consumption.  In contrast, both DBPedia and Seqweb implement machine-readable knowledge graphs.

This framing is easily visualied by laying out the analogy as a 2-by-2 matrix.

<!--
                   General Info    Sequences  
                 +--------------+-------------+
Natural Language |  Wikipedia   |    OEIS     |
                 +--------------+-------------+
Knowledge Graph  |   DBpedia    |   SeqWeb    |
                 +--------------+-------------+
-->

|                     |              |                |
|---------------------|--------------|----------------|
|                     | _sequences_  | _general info_ |
| _knowledge graphs_  | ***SeqWeb*** | **DBpedia**    | 
| _linked documents_  | **OEIS**     | **Wikipedia**  |

Here's a brief recap of each:

### Wikipedia
Good ol' Wikipedia is familiar to almost everyone, but we might summarize it as a community-curated online encyclopedia of general information subject matter.  It is presented as web pages of formatted natural languge content, along with associated graphics, references to relevant external resources and links to other Wikipedia articles.  For more general background about wikipedia, see (of course) https://en.wikipedia.org/wiki/Wikipedia.

### OEIS
The OEIS is also a comprehensive, community-curated online encyclopedia presented as rich web pages, supported by a worldwide community of contributors and editors.  However the subject matter domain of the OEIS is specialized around integer sequences.  Despite this, in practice it has effectively proven to be a very broad catalog of knowledge in discrete mathematics, number theory and related areas.  

A unique aspect of the OEIS is that its articles can be retrieved by their sequence's numerical pattern, as well as more conventional search queries.  This not only makes the OEIS a valuable content-addressible knowledge resource for general users that overcomes barriers of academic jargon, it has led to many seredipitous discoveries for mathematical researchers.

For general information regarding the OEIS see  Wikipedia's article https://en.wikipedia.org/wiki/On-Line_Encyclopedia_of_Integer_Sequences, which includes some illustrative examples and other details.

The OEIS itself also supports a wiki, at https://oeis.org/wiki/Main_Page.  The OEIS wiki includes much additional information, including a helpful orientation page https://oeis.org/wiki/Welcome.

Further, anyone who registers as an OEIS user is assigned a "user page" in the wiki, for example https://oeis.org/wiki/User:N._J._A._Sloane (whose Wikipedia page is at https://en.wikipedia.org/wiki/Neil_Sloane).  These user pages can host user-provided content to supplement the entries, and the entries themselves use these URLs to help assign authorship provenance.  Thus the OEIS is a nexus of not only mathematical information, but a community of people reflected in the web.

### DBpedia
DBpedia embodies Wikipedia as a knowledge graph, and is a premier examplar of Tim Berners-Lee's vision of the Semantic Web:

_"...the Semantic Web is to enable people to share content ... beyond the boundaries of **strings** to the concept of **things**.”_<br>
        —- Tim Berners-Lee, _Linked Data - Design Issues_, W3C, July 2006

DBpedia might be described as an extensive, community-curated semantic knowledge base that augments Wikipedia. 
It provides machine-readable access to Wikipedia's the underlying human-readable information.  It is implemented using the advanced data technologies (such as RDF, SPARQL, etc.) developed and standardized by the W3C and the semantic web community.  It models the Wikipedia as an interconnected knowledge graph open for computational exploration and integration.  

Semantic technologies can bridge the natural expressiveness of human language to the power and utility of modern structured data and high-performance processing.  This has become especially relevant with the advent of LLMs and other AI technologies.

An introduction to DBpedia can be found in the Wikipedia article https://en.wikipedia.org/wiki/DBpedia.  The DBPedia site itself also hosts informative pages, including https://www.dbpedia.org/about/.

And for an actual concrete example, here is the actual DBpedia page corresponding to Wikipedia's DBpedia article: https://dbpedia.org/page/DBpedia.  

Note that you can easily get from one URL to the other simply by switching the "prefix" part of the URL,  attaching the same "DBpedia" suffix.  For less self-referential examples, try suffixing "Neil_Sloane" or "On-Line_Encyclopedia_of_Integer_Sequences" instead.

### SeqWeb
