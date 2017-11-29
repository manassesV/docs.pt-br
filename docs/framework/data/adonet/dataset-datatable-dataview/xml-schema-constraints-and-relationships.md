---
title: "Relações e restrições de esquema XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a324c3b7f24d3395382067ea5581313af58e13f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="7b3fe-102">Relações e restrições de esquema XML</span><span class="sxs-lookup"><span data-stu-id="7b3fe-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="7b3fe-103">Em um esquema de linguagem XSD de definição de esquema XML, você pode especificar restrições (exclusivos, restrições de chave e keyref) e relações (usando o **msdata:Relationship** anotação).</span><span class="sxs-lookup"><span data-stu-id="7b3fe-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="7b3fe-104">Este tópico explica como as restrições e relações especificadas em um esquema XML são interpretadas para gerar o <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="7b3fe-105">Em geral, em um esquema XML, especifique o **msdata:Relationship** anotação se desejar gerar somente os relacionamentos no **conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="7b3fe-106">Para obter mais informações, consulte [gerar relações de conjunto de dados de esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="7b3fe-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="7b3fe-107">Você especifica restrições (exclusivo, chave e keyref) se você deseja gerar restrições no **conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="7b3fe-108">Observe que as restrições de chave e keyref também são usadas para gerar relações, conforme explicado mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="7b3fe-109">Gerando uma relação de chave e keyref restrições</span><span class="sxs-lookup"><span data-stu-id="7b3fe-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="7b3fe-110">Em vez de especificar o **msdata:Relationship** anotação, você pode especificar restrições de chave e keyref, que são usadas durante o processo de mapeamento de esquema XML para gerar o nãoapenasasrestrições,mastambémarelação **Conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="7b3fe-111">No entanto, se você especificar `msdata:ConstraintOnly="true"` no **keyref** elemento, o **DataSet** incluirá somente as restrições e não incluirá a relação.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="7b3fe-112">O exemplo a seguir mostra um esquema XML que inclui **ordem** e **OrderDetail** elementos, que não estão aninhados.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="7b3fe-113">O esquema também especifica as restrições de chave e keyref.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-113">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="7b3fe-114">O **DataSet** que é gerado durante o esquema XML que inclui o processo de mapeamento de **ordem** e **OrderDetail** tabelas.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="7b3fe-115">Além disso, o **DataSet** inclui relações e restrições.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="7b3fe-116">O exemplo a seguir mostra essas relações e restrições.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="7b3fe-117">Observe que o esquema não especificar o **msdata:Relationship** anotação; em vez disso, as restrições de chave e keyref são usadas para gerar a relação.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="7b3fe-118">No exemplo anterior de esquema, o **ordem** e **OrderDetail** elementos não estão aninhados.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="7b3fe-119">No exemplo de esquema a seguir, esses elementos são aninhados.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="7b3fe-120">No entanto, nenhuma **msdata:Relationship** anotação é especificada; portanto, uma relação implícita é assumida.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="7b3fe-121">Para obter mais informações, consulte [implícita relações entre aninhados esquema elementos do mapa](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="7b3fe-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="7b3fe-122">O esquema também especifica as restrições de chave e keyref.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="7b3fe-123">O **DataSet** resultante do processo de mapeamento de esquema XML inclui duas tabelas:</span><span class="sxs-lookup"><span data-stu-id="7b3fe-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="7b3fe-124">O **DataSet** também inclui duas relações (uma baseada no **msdata:relationship** anotação e o outro com base nas restrições de chave e keyref) e várias restrições.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="7b3fe-125">O exemplo a seguir mostra as relações e restrições.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="7b3fe-126">Se uma restrição keyref que faz referência a uma tabela aninhada contém o **msdata:IsNested = "true"** anotação, o **DataSet** criará uma relação aninhada único com base na restrição keyref e o restrição de chave exclusiva/relacionada.</span><span class="sxs-lookup"><span data-stu-id="7b3fe-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3fe-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7b3fe-127">See Also</span></span>  
 [<span data-ttu-id="7b3fe-128">Derivando a estrutura relacional do conjunto de dados de esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="7b3fe-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="7b3fe-129">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="7b3fe-129">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>