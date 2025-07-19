## ***SeqWeb*** _is to the_ **OEIS** _as_ **DBpedia** _is to_ **Wikipedia**.

This terse framing analogy can be useful for "quadrangulating" on the goals and substance of the SeqWeb project.  

All four components of the analogy are web resources addressable via Internet domains: `seqweb.org`, `oeis.org`, `dbpedia.org` and `wikipedia.org` respectively.

These four web entities can be organized naturally along two axes: _subject focus_ and _content type_. 

- The _subject focus_ of both Wikipedia and DBpedia is general information, while for both the OEIS and SeqWeb it is the specialized area of mathematical integer sequences.

- Along the _content type_ dimension both Wikipedia and the OEIS present rich web pages of interlinked documents intended for human consumption.  In contrast, both DBPedia and Seqweb implement machine-readable knowledge graphs.

This framing is easily visualized by laying out the analogy as a 2-by-2 matrix.

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
Good ol' Wikipedia is familiar to almost everyone, but we might summarize it as a community-curated online encyclopedia of general information subject matter.  It is presented as web pages of formatted natural language content, along with associated graphics, references to relevant external resources and links to other Wikipedia articles.  For more general background about wikipedia, see (of course) https://en.wikipedia.org/wiki/Wikipedia.

### OEIS
The OEIS is also a comprehensive, community-curated online encyclopedia presented as rich web pages, supported by a worldwide community of contributors and editors.  However, the subject matter domain of the OEIS is specialized around integer sequences.  Despite this, in practice it has effectively proven to be a very broad catalog of knowledge in discrete mathematics, number theory and related areas.  

A unique aspect of the OEIS is that its articles can be retrieved by their sequence's numerical pattern, as well as more conventional search queries.  This not only makes the OEIS a valuable content-addressable knowledge resource for general users that overcomes barriers of academic jargon, it has led to many serendipitous discoveries for mathematical researchers.

For general information regarding the OEIS, see Wikipedia's article https://en.wikipedia.org/wiki/On-Line_Encyclopedia_of_Integer_Sequences, which includes some illustrative examples and other details.

The OEIS itself also supports a wiki, at https://oeis.org/wiki/Main_Page.  The OEIS wiki includes much additional information, including a helpful orientation page https://oeis.org/wiki/Welcome.

Further, anyone who registers as an OEIS user is assigned a "user page" in the wiki; for example https://oeis.org/wiki/User:N._J._A._Sloane (whose Wikipedia page is at https://en.wikipedia.org/wiki/Neil_Sloane).  These user pages can host user-provided content to supplement the entries, and the entries themselves use these URLs to help assign authorship provenance.  Thus the OEIS is a nexus of not only mathematical information, but a community of people, reflected in the web.

### DBpedia
DBpedia embodies Wikipedia as a knowledge graph, and is a premier exemplar of Tim Berners-Lee's vision of the Semantic Web:

_"...the Semantic Web is to enable people to share content ... beyond the boundaries of **strings** to the concept of **things**.”_<br>
        —- Tim Berners-Lee, _Linked Data - Design Issues_, W3C, July 2006

DBpedia might be described as an extensive, community-curated semantic knowledge base that augments Wikipedia. 
It provides machine-readable access to Wikipedia's underlying human-readable information.  It is implemented using the advanced data technologies (such as RDF, SPARQL, etc.) developed and standardized by the W3C and the semantic web community.  It models the Wikipedia as an open interconnected knowledge graph for computational exploration and integration.  

Semantic technologies can bridge the natural expressiveness of human language to the power and utility of modern structured data and high-performance processing.  This has become especially relevant with the advent of LLMs and other AI technologies.

An introduction to DBpedia can be found in the Wikipedia article https://en.wikipedia.org/wiki/DBpedia.  The DBPedia site itself also hosts informative pages, including https://www.dbpedia.org/about/.

For a concrete example, here is the actual DBpedia page corresponding to Wikipedia's DBpedia article: https://dbpedia.org/page/DBpedia.  

Note that you can easily get from one URL to the other simply by switching the "prefix" part of the URL and attaching the same "DBpedia" suffix.  For less self-referential examples, try suffixing "Neil_Sloane" or "On-Line_Encyclopedia_of_Integer_Sequences" instead.

### SeqWeb
Thus the goal of the SeqWeb project is to develop and provide a companion web resource for the OEIS, akin to how DBpedia extends Wikipedia.  

When fully operational, SeqWeb can be expected to tangibly include
- a knowledge graph implemented in a publicly-hosted database containing standardized linked open data
- an open ontology describing the semantics and schemas of the SeqWeb data for human and machine (eg AI) use
- a web service providing APIs and both conventional (REST) and semantic (SPARQL) query endpoints for applications
- infrastructure and automation for syncing SeqWeb with the OEIS
- support for ongoing "open source" development processes and the contributing community
- a technical framework encouraging extensions and experiments

#### Tenet of Independence of the OEIS from SeqWeb
A central tenet of the project is that SeqWeb augments the OEIS wholly independently and additively, without burdening or impacting the OEIS in any way.  No modifications of any kind to the OEIS's style, content, technology or operations are needed or desired.  Just as Wikipedia's readers and staff need not be concerned with the existence of DBpedia, the OEIS and its community of users and editors will continue as always -- _"It ain't broke; don't fix it."_

#### Syncing SeqWeb with the OEIS via Github
Conveniently, there is no requirement that SeqWeb keep up in real time with changes to the OEIS (just as for DBpedia with Wikipedia).  But as it happens, the OEIS uploads an update to its complete snapshot to Github every few days.  This update is applied to the repository at https://github.com/oeis/oeisdata.  This repo's directory structure maps each OEIS article to a predictable Github file path URL.  For example the OEIS sequence at URL https://oeis.org/A046970 is memorialized in the `oeisdata` repo as the file https://github.com/oeis/oeisdata/blob/main/seq/A046/A046970.seq.  SeqWeb can therefore track the `oeisdata` repo to synchronize its model with the OEIS at will, to get the updated _base_ model.  

Additionally, it is expected that SeqWeb will also support a collection of diverse processing modules whose purpose is to augment the _base model_ with additional _derived_ information.  For example, a module might apply a natural language library to a particular section of an OEIS article's data (say the bibliographic citations) in order to extract associated named entities (say authors, or journals) to be represented as triples in the SeqWeb knowledge graph.  These modules will also need to be re-run when their source data changes.  The detailed architecture for these modules, and the framework for orchestrating their application, is one of the more interesting tasks awaiting development.

Development and delivery for SeqWeb are also supported by Github repos, under the https://github.com/seqweb/ prefix:

- `seqwebdata` is intended to contain a snapshot of SeqWeb's knowledge graph, synchronized to track with changes to `oeisdata` and reflecting its content and structure

- `seqwebcode` is the development repo, and is intended as the source control for everything else in the SeqWeb system

[Note: currently, during initial development, SeqWeb's formal ontologies and related collateral (such as vocabularies, modeling guides, etc) are assigned to the `seqwebcode/ontology/` folder -- however we may want to revisit this and migrate them into `seqwebdata` instead]

#### Possible Benefits to the OEIS from SeqWeb
While it's impossible to predict what innovative uses for the OEIS's trove of knowledge SeqWeb will inspire, interesting outcomes can be anticipated in a few areas:

**Rigor** SeqWeb and the semantic web modeling disciplines can provide an additional level of precision to that already enjoyed by the OEIS as a mathematical reference.  While not quite at the level of, say, a proof checker, practices such as registering definitions of terms being used in vocabularies and specifying their relationships using formal ontologies will tend to raise overall quality.  For example it can help ameliorate ambiguities like whether a certain string token refers to a mathematical function, its approximate implementation in a particular programming language, or something else.

Even relatively banal statements can be made more precise and usable.  For example a sequence with a definition including text like "...primes such that..." can be expressed precisely:
```
    oeis:A000668    seq:subsetOf    oeis:A000040 .
```

**AI**  In a related vein, SeqWeb may be used to help control LLMs and turn them, in the OEIS context, from unreliable slop generators toward greater utility -- for example they could be part of a natural language query interface to the OEIS, implemented using the "Graph-RAG" pattern.

**Extensions**  Perennially, users of the OEIS come up with interesting ideas for possible features, motivated by specialized interests and use cases.  Typical examples are proposals for new keywords, perhaps accompanied by ideas like parameterizing them.  Sadly these enthusiasms usually have to be squelched, since disrupting the current underlying legacy data model would be taxing, and the consequent maintenance burden unsupportable.

SeqWeb can provide a constructive alternative avenue for these worthy proposals.  Since a knowledge graph can host an unbounded number of new assertions, and triple subgraphs provide a fully flexible yet highly structured construction medium, users can design accretive extensions without disrupting pre-existing OEIS schemas.

**Federation**  Moreover, unlike traditional information, knowledge graphs need not be confined to single datastores.  Since triples are built entirely from URLs (IRIs actually) they can, and do, reference resources that can be anywhere on the World Wide Web.  The SPARQL query language includes features that cause endpoints on external hosts to be seamlessly queryable as though they were simply subgraphs.  For example a single query expression might find all sequences authored by someone's doctoral students, who would be obtained from DBpedia.
Here's a simplified example showing a federated query issued to my local SPARQL endpoint that looks up a DBpedia entry:
```
SELECT ?person ?name WHERE {
  SERVICE <http://dbpedia.org/sparql> {
    ?person a foaf:Person .
    ?person rdfs:label ?name .
    FILTER (LANG(?name) = "en" && regex(?name, "Neil", "i") && regex(?name, "Sloane", "i")) .
  } 
} 
```
This returns
```
<http://dbpedia.org/resource/Neil_Sloane>   "Neil Sloane"@en
```

This means in particular that extensions can be entirely implemented and hosted by others.  For example a set of specialized relationships between sequences could be identified by an academic researcher, embodied as a knowledge graph maintained at their home institution, and made fully available via federation with SeqWeb.

**Frontier Mathematics** SeqWeb will enable and encourage new sorts of explorations.  For example sequence "transforms" are a longstanding concept in the OEIS.  But today the only way to express these relationships is with natural language text commentary like "a(n) is the Möbius transform of the primes."  In SeqWeb this could be modeled concretely as a triple like
```
    oeis:A007444    seq:möbiusTransformOf   oeis:A000040 .
```

with the SeqWeb ontology containing definitions like
```
    seq:möbiusTransformOf   rdf:type        seq:Transform ;
                            seq:definition  oeis:wiki/Möbius_transform ;
                            rdfs:domain     seq:Sequence ;
                            rdfs:range      seq:Sequence ;
                            owl:inverseOf   seq:hasMöbiusTransform ;
                            ... .
```
One could imagine a project that systematically walks through all the sequences, applying Superseeker transforms, and making the appropriate assertions into the SeqWeb graph whenever it gets a hit.
