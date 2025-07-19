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

Here's a thumbnail description of each component, with links to more information:

### Wikipedia
Good ol' Wikipedia is familiar to almost everyone, but we might summarize it as a community-curated online encyclopedia of general information subject matter.  It is presented as web pages of formatted natural languge content, along with associated graphics, references to relevant external resources and links to other Wikipedia articles.  For more general background about wikipedia, see (of course) https://en.wikipedia.org/wiki/Wikipedia.

### OEIS
The OEIS is also a comprehensive, community-curated online encyclopedia presented as rich web pages, supported by a worldwide community of contributors and editors.  However the subject matter domain of the OEIS is specialized around integer sequences.  Despite this, in practice it has effectively proven to be a very broad catalog of knowledge in discrete mathematics, number theory and related areas.  

A unique aspect of the OEIS is that its articles can be retrieved by their sequence's numerical pattern, as well as more conventional search queries.  This not only makes the OEIS a valuable content-addressible knowledge resource for general users that overcomes barriers of academic jargon, it has led to many seredipitous discoveries for mathematical researchers.

For general information regarding the OEIS see  Wikipedia's article https://en.wikipedia.org/wiki/On-Line_Encyclopedia_of_Integer_Sequences, which includes some illustrative examples and other details.

The OEIS itself also supports a wiki, at https://oeis.org/wiki/Main_Page.  The OEIS wiki includes much additional information, including a helpful orientation page https://oeis.org/wiki/Welcome.

Further, anyone who registers as an OEIS user is assigned a "user page" in the wiki, for example https://oeis.org/wiki/User:N._J._A._Sloane (whose Wikipedia page is at https://en.wikipedia.org/wiki/Neil_Sloane).  These user pages can host user-provided content to supplement the entries, and the entries themselves use these URLs to help assign authorship provenance.  Thus the OEIS is a nexus of not only mathematical information, but a community of people, reflected in the web.

### DBpedia
DBpedia embodies Wikipedia as a knowledge graph, and is a premier examplar of Tim Berners-Lee's vision of the Semantic Web:

_"...the Semantic Web is to enable people to share content ... beyond the boundaries of **strings** to the concept of **things**.”_<br>
        —- Tim Berners-Lee, _Linked Data - Design Issues_, W3C, July 2006

DBpedia might be described as an extensive, community-curated semantic knowledge base that augments Wikipedia. 
It provides machine-readable access to Wikipedia's underlying human-readable information.  It is implemented using the advanced data technologies (such as RDF, SPARQL, etc.) developed and standardized by the W3C and the semantic web community.  It models the Wikipedia as an open interconnected knowledge graph for computational exploration and integration.  

Semantic technologies can bridge the natural expressiveness of human language to the power and utility of modern structured data and high-performance processing.  This has become especially relevant with the advent of LLMs and other AI technologies.

An introduction to DBpedia can be found in the Wikipedia article https://en.wikipedia.org/wiki/DBpedia.  The DBPedia site itself also hosts informative pages, including https://www.dbpedia.org/about/.

For a concrete example, here is the actual DBpedia page corresponding to Wikipedia's DBpedia article: https://dbpedia.org/page/DBpedia.  

Note that you can easily get from one URL to the other simply by switching the "prefix" part of the URL,  attaching the same "DBpedia" suffix.  For less self-referential examples, try suffixing "Neil_Sloane" or "On-Line_Encyclopedia_of_Integer_Sequences" instead.

### SeqWeb
Thus the goal of the SeqWeb project is to develop and provide a companion web resource for the OEIS, akin to how DBpedia extends Wikipedia.  

When fully operational SeqWeb can be expected to tangibly include
- a knowledge graph implemented in a publicly-hosted database containing standardized linked open data
- an open ontology describing the semantics and schemas of the SeqWeb data for human and machine (eg AI) use
- a web service providing APIs and both conventional (REST) and semantic (SPARQL) query endpoints for applications
- infrastructure and automation for syncing SeqWeb with the OEIS
- support for ongoing "open source" development processes and the contribiuting community
- a technical framework encouraging extensions and experiments

#### Tenet of Independence of the OEIS from SeqWeb
A central tenet of the project is that SeqWeb augments the OEIS wholly indepedently and additively, without burdening or impacting the OEIS in any way.  No modifications of any kind to the OEIS's style, content, technology or operations are needed or desired.  Just as Wikipedia's readers and staff need not be concerned with the existence of DBpedia, the OEIS and its community of users and editors will continue as always -- _"It ain't broke; don't fix it."_

#### Synching SeqWeb with the OEIS via Github
Conveniently there is no requirement that SeqWeb keep up in real time with changes to the OEIS (just as for DBpedia with Wikipedia).  But as it happens, the OEIS uploads an update to its complete snapshot to Github every few days.  This update is applied to the repository at https://github.com/oeis/oeisdata.  This repo's directory structure maps each OEIS article to a predictable Github file path URL.  For example the OEIS sequence at URL https://oeis.org/A046970 is memorialized in the `oeisdata` repo as the file https://github.com/oeis/oeisdata/blob/main/seq/A046/A046970.seq.  SeqWeb can therefore track the `oeisdata` repo to synchronize its model with the OEIS at will, to get the updated _base_ model.  

Additionally, it is expected that SeqWeb will also support a collection of diverse processing modules whose purpose is to augment the _base model_ with additional _derived_ information.  For example a module might apply a natural language library to a particular section of the an OEIS article's data (say the bibliographic citations) in order to extract associated named entities (say authors, or journals) to be represented as triples in the SeqWeb knowledge graph.  These modules will also need to be re-run when their source data changes.  The detailed architecture for these modules, and the framework for orchestrating their application, is one of the more interesting tasks awaiting development.

Development and delivery for SeqWeb are also supported by Github repos, under the https://github.com/seqweb/ prefix:

- `seqwebdata` is intended to contain a snapshot of SeqWeb's knowledge graph, synchronized to track with changes to `oeisdata` and reflecting its content and structure

- `seqwebcode` is the development repo, and is intended as the source control for everything else in the SeqWeb system

[Note: currently, during initial development, SeqWeb's formal ontologies and related collateral (such as vocabularies, modeling guides, etc) are assigned to the `seqwebcode/ontology/` folder -- however we may want to revisit this and migrate them into `seqwebdata` instead]

#### Benefits to the OEIS from SeqWeb
While it's impossible to predict what innovative uses for the OEIS's trove of knowledge SeqWeb will inspire, interesting outcomes can be anticipated in a few areas:

**Rigor** 

**AI**

**Extensions**

**Federation**
