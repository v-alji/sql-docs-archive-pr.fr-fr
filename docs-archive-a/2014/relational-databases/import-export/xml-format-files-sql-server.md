---
title: Fichiers de format XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612831"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="5ac5f-102">Fichiers de format XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="5ac5f-103">fournit un schéma XML qui définit la syntaxe des *fichiers de format XML* à utiliser pour l'importation en bloc de données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ac5f-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="5ac5f-104">Les fichiers de format XML doivent respecter ce schéma, qui est défini en langage XSDL (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="5ac5f-105">Les fichiers de format XML ne sont pris en charge que si les outils [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installés conjointement avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="5ac5f-106">Vous pouvez utiliser un fichier de format XML avec une commande **bcp**, une instruction BULK INSERT ou une instruction INSERT... Instruction SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="5ac5f-107">La commande **bcp** vous permet de générer automatiquement un fichier de format XML pour une table. Pour plus d’informations, voir [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-108">Deux types de fichiers de format sont pris en charge pour l’exportation et l’importation en bloc : les *fichiers de format non XML* et les *fichiers de format XML*.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="5ac5f-109">Les fichiers de format XML offrent une solution souple et puissante aux fichiers de format non XML.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="5ac5f-110">Pour plus d’informations sur les fichiers de format non-XML, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="5ac5f-111">Avantages des fichiers de format XML</span><span class="sxs-lookup"><span data-stu-id="5ac5f-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="5ac5f-112">Les fichiers de format XML sont autodescriptifs, ce qui en facilite la lecture, la création et l'extension.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="5ac5f-113">Ils sont lisibles, ce qui permet de facilement comprendre la manière dont les données sont interprétées lors des opérations en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="5ac5f-114">Les fichiers de format XML contiennent les types de données des colonnes cibles.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="5ac5f-115">L'encodage XML décrit clairement les types de données et les éléments de données du fichier de données ainsi que la correspondance entre les éléments de données et les colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="5ac5f-116">Ceci permet d'établir une séparation entre la manière dont les données sont représentées dans le fichier de données et le type de données associé à chaque champ du fichier.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="5ac5f-117">Par exemple, si un fichier de données contient une représentation en caractères des données, le type de colonne SQL correspondant est perdu.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="5ac5f-118">Un format de fichier XML permet de charger un champ qui contient un seul type de données LOB à partir d'un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="5ac5f-119">Un fichier de format XML peut être amélioré tout en demeurant compatible avec ses versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="5ac5f-120">En outre, la clarté de l'encodage XML facilite la création de plusieurs fichiers de format pour un fichier de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="5ac5f-121">Cela est utile si vous devez mapper tout ou partie des champs de données à des colonnes de différentes tables ou vues.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="5ac5f-122">La syntaxe XML ne dépend pas de la direction dans laquelle s'effectue l'opération : elle est la même qu'il s'agisse d'une exportation ou d'une importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="5ac5f-123">Vous pouvez utiliser les fichiers de format XML pour importer des données en bloc dans des tables ou dans des vues non partitionnées et pour exporter des données en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="5ac5f-124">Pour la fonction OPENROWSET (BULK…), il n'est pas obligatoire de spécifier une table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="5ac5f-125">En effet, cette fonction s'appuie sur le fichier de format XML pour lire les données d'un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5ac5f-126">Une table cible est nécessaire avec la commande **bcp** et l’instruction BULK INSERT, qui utilise les colonnes de la table cible pour effectuer la conversion de type.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="5ac5f-127">Structure des fichiers de format XML</span><span class="sxs-lookup"><span data-stu-id="5ac5f-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="5ac5f-128">À l'image d'un fichier de format non-XML, un fichier de format XML définit le format et la structure des champs de données d'un fichier de données et mappe ces champs avec les colonnes d'une table cible spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="5ac5f-129">Un fichier de format XML possède deux composants principaux, \<RECORD> et \<ROW> :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="5ac5f-130">Le composant \<RECORD> décrit les données telles qu’elles sont stockées dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="5ac5f-131">Chaque élément \<RECORD> contient un ensemble d’un ou de plusieurs éléments \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="5ac5f-132">Ces éléments correspondent aux champs du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="5ac5f-133">La syntaxe de base est la suivante :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="5ac5f-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="5ac5f-135">Chaque élément \<FIELD> décrit le contenu d’un champ de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="5ac5f-136">Un champ ne peut être mappé qu'à une seule colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="5ac5f-137">Tous les champs ne doivent pas être mappés à des colonnes.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="5ac5f-138">Un champ d'un fichier de données peut être de longueur fixe/variable ou terminé par un caractère.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="5ac5f-139">Une *valeur de champ* peut être représentée par : un caractère (représentation sur un octet), un caractère large (représentation Unicode sur deux octets), un nom de fichier ou dans un format de base de données natif.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="5ac5f-140">Si une valeur de champ est représentée par un nom de fichier, celui-ci pointe vers le fichier qui contient la valeur d'une colonne BLOB de la table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="5ac5f-141">Le composant \<ROW> explique comment créer des lignes de données à partir d’un fichier de données quand les données du fichier sont importées dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac5f-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="5ac5f-142">Un élément \<ROW> contient un ensemble d’éléments \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="5ac5f-143">Ces éléments correspondent à des colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-143">These elements correspond to table columns.</span></span> <span data-ttu-id="5ac5f-144">La syntaxe de base est la suivante :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="5ac5f-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="5ac5f-146">Chaque élément \<COLUMN> ne peut être mappé qu’à un seul champ du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="5ac5f-147">L’ordre des éléments \<COLUMN> dans l’élément \<ROW> définit l’ordre dans lequel ils sont renvoyés par l’opération en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="5ac5f-148">Le fichier de format XML attribue à chaque élément \<COLUMN> un nom local qui n’a aucune relation avec la colonne dans la table cible d’une opération d’importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="5ac5f-149">Syntaxe de schéma pour les fichiers de format XML</span><span class="sxs-lookup"><span data-stu-id="5ac5f-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="5ac5f-150">Cette section contient un récapitulatif des éléments et des attributs du schéma XML des fichiers de format XML.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="5ac5f-151">La syntaxe d'un fichier de format ne dépend pas de la direction dans laquelle s'effectue l'opération : elle est la même qu'il s'agisse d'une exportation ou d'une importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="5ac5f-152">Cette section examine également comment l’importation en bloc utilise les éléments \<ROW> et \<COLUMN>, et comment inclure la valeur xsi:type d’un élément dans un jeu de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="5ac5f-153">Pour voir comment la syntaxe correspond aux fichiers de format XML réels, consultez [Exemples de fichiers de format XML](#SampleXmlFFs), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-154">Vous pouvez modifier un fichier de format de manière à effectuer une importation en bloc à partir d'un fichier de données dans lequel le nombre et/ou l'ordre des champs diffèrent du nombre et/ou de l'ordre des colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="5ac5f-155">Pour plus d’informations, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="5ac5f-156">Syntaxe de base du schéma XML</span><span class="sxs-lookup"><span data-stu-id="5ac5f-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="5ac5f-157">Ces instructions de syntaxe illustrent uniquement les éléments (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> et \<COLUMN>), ainsi que leurs attributs de base.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="5ac5f-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="5ac5f-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-160">Les attributs supplémentaires qui sont associés à la valeur de xsi:type dans un élément \<FIELD> ou \<COLUMN> sont décrits ultérieurement dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="5ac5f-161">Éléments du schéma</span><span class="sxs-lookup"><span data-stu-id="5ac5f-161">Schema Elements</span></span>  
 <span data-ttu-id="5ac5f-162">Cette section résume l'objet de chaque élément que le schéma XML définit pour les fichiers de format XML.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="5ac5f-163">Les attributs sont décrits dans des sections séparées plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="5ac5f-164">Élément format-file qui définit la structure d'enregistrement d'un fichier de données spécifique et sa correspondance aux colonnes d'une ligne dans la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="5ac5f-165">Définit un élément complexe contenant un ou plusieurs éléments \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="5ac5f-166">L'ordre dans lequel les champs sont déclarés dans le fichier de format est celui dans lequel ces champs apparaissent dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="5ac5f-167">Définit un champ dans le fichier de données, qui contient des données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="5ac5f-168">Les attributs de cet élément sont décrits dans la section [Attributs de l’élément \<FIELD>](#AttrOfFieldElement), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="5ac5f-169">Définit un élément complexe contenant un ou plusieurs éléments \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="5ac5f-170">L’ordre des éléments \<COLUMN> est indépendant de l’ordre des éléments \<FIELD> dans une définition RECORD.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="5ac5f-171">En revanche, l’ordre des éléments \<COLUMN> dans un fichier de format détermine l’ordre des colonnes de l’ensemble de lignes résultant.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="5ac5f-172">Les champs de données sont chargés dans l’ordre de déclaration des éléments \<COLUMN> correspondants dans l’élément \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="5ac5f-173">Pour plus d’informations, consultez [Comment l’importation en bloc utilise l’élément \<ROW>](#HowUsesROW), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="5ac5f-174">Définit une colonne comme élément (\<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="5ac5f-175">Chaque élément \<COLUMN> correspond à un élément \<FIELD> (dont l’ID est spécifié dans l’attribut SOURCE de l’élément \<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="5ac5f-176">Les attributs de cet élément sont décrits dans la section [Attributs de l’élément \<COLUMN>](#AttrOfColumnElement), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="5ac5f-177">Consultez également [Comment l’importation en bloc utilise l’élément \<COLUMN>](#HowUsesColumn), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="5ac5f-178">Requis pour terminer le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><a name="AttrOfFieldElement"></a> <span data-ttu-id="5ac5f-179">Attributs de l'élément \<FIELD></span><span class="sxs-lookup"><span data-stu-id="5ac5f-179">Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="5ac5f-180">Cette section décrit les attributs de l’élément \<FIELD>, qui sont récapitulés dans la syntaxe de schéma suivante :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="5ac5f-181"><FIELD</span><span class="sxs-lookup"><span data-stu-id="5ac5f-181"><FIELD</span></span>  
  
 <span data-ttu-id="5ac5f-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="5ac5f-183">xsi **:** type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="5ac5f-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="5ac5f-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="5ac5f-186">[MAX_LENGTH **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="5ac5f-187">[Collation **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="5ac5f-188">[TERMINATOR **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="5ac5f-189">Chaque élément \<FIELD> est indépendant des autres.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="5ac5f-190">Un champ est décrit en termes des attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="5ac5f-191">Attribut FIELD</span><span class="sxs-lookup"><span data-stu-id="5ac5f-191">FIELD Attribute</span></span>|<span data-ttu-id="5ac5f-192">Description</span><span class="sxs-lookup"><span data-stu-id="5ac5f-192">Description</span></span>|<span data-ttu-id="5ac5f-193">Facultatif /</span><span class="sxs-lookup"><span data-stu-id="5ac5f-193">Optional /</span></span><br /><br /> <span data-ttu-id="5ac5f-194">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="5ac5f-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="5ac5f-196">Spécifie le nom logique du champ dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="5ac5f-197">L'ID d'un champ est la clé utilisée pour y faire référence.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="5ac5f-198"><champ ID **= " *`fieldID`* "**/> correspond à <colonne source **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="5ac5f-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="5ac5f-199">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-199">Required</span></span>|  
|<span data-ttu-id="5ac5f-200">xsi : type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="5ac5f-201">Il s'agit d'une construction XML (utilisée comme un attribut) qui identifie le type de l'instance de l'élément.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="5ac5f-202">La valeur de *fieldType* détermine de quels attributs facultatifs (ci-dessous) vous avez besoin dans une instance donnée.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="5ac5f-203">Obligatoire (selon le type de données)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="5ac5f-204">LONGUEUR **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="5ac5f-205">Cet attribut définit la longueur pour une instance d'un type de données à longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="5ac5f-206">Cette valeur de *n* doit être un entier positif.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="5ac5f-207">Facultatif sauf s'il est requis par la valeur xsi:type</span><span class="sxs-lookup"><span data-stu-id="5ac5f-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="5ac5f-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="5ac5f-209">Cet attribut définit la longueur de préfixe pour une représentation de données binaires.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="5ac5f-210">La valeur PREFIX_LENGTH, *p*, doit correspondre à l’une des valeurs suivantes : 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="5ac5f-211">Facultatif sauf s'il est requis par la valeur xsi:type</span><span class="sxs-lookup"><span data-stu-id="5ac5f-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="5ac5f-212">MAX_LENGTH **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="5ac5f-213">Cet attribut est le nombre maximal d'octets pouvant être stockés dans un champ donné.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="5ac5f-214">Sans table cible, la longueur maximale de la colonne est inconnue.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="5ac5f-215">L'attribut MAX_LENGTH limite la longueur maximale d'une colonne de caractères en sortie, limitant ainsi le stockage alloué pour la valeur de la colonne.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="5ac5f-216">Ceci est particulièrement pratique lors de l'utilisation de l'option BULK de la fonction OPENROWSET dans une clause SELECT FROM.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="5ac5f-217">Cette valeur de *m* doit être un entier positif.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="5ac5f-218">Par défaut, la longueur maximale est de 8 000 caractères pour une colonne **char** et de 4 000 caractères pour une colonne **nchar** .</span><span class="sxs-lookup"><span data-stu-id="5ac5f-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="5ac5f-219">Facultatif</span><span class="sxs-lookup"><span data-stu-id="5ac5f-219">Optional</span></span>|  
|<span data-ttu-id="5ac5f-220">COLLATION **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="5ac5f-221">COLLATION est uniquement autorisé pour les champs caractères.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="5ac5f-222">Pour obtenir la liste des noms du classement SQL, consultez [Nom du classement SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="5ac5f-223">Facultatif</span><span class="sxs-lookup"><span data-stu-id="5ac5f-223">Optional</span></span>|  
|<span data-ttu-id="5ac5f-224">TERMINATEUR **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="5ac5f-225">Cet attribut spécifie la marque de fin d'un champ de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="5ac5f-226">La marque de fin peut être n'importe quel caractère.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-226">The terminator can be any character.</span></span> <span data-ttu-id="5ac5f-227">La marque de fin doit être un caractère unique ne faisant pas partie des données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="5ac5f-228">Par défaut, la marque de fin de champ est le caractère tabulation (représenté par \t).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="5ac5f-229">Pour représenter une marque de paragraphe, utilisez \r\n.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="5ac5f-230">Utilisé uniquement avec un xsi:type de données caractères, qui nécessite cet attribut</span><span class="sxs-lookup"><span data-stu-id="5ac5f-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><a name="XsiTypeValuesOfFIELD"></a> <span data-ttu-id="5ac5f-231">Valeurs Xsi:type de l’élément \<FIELD></span><span class="sxs-lookup"><span data-stu-id="5ac5f-231">Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="5ac5f-232">La valeur xsi:type est une construction XML (utilisée comme un attribut) qui identifie le type de données d'une instance d'un élément.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="5ac5f-233">Pour plus d'informations sur l'utilisation de cette valeur, consultez « Placement de la valeur xsi:type dans un ensemble de données », plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="5ac5f-234">La valeur xsi:type de l’élément \<FIELD> prend en charge les types de données suivants.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="5ac5f-235">Valeurs xsi:type \<FIELD></span><span class="sxs-lookup"><span data-stu-id="5ac5f-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="5ac5f-236">Attribut(s) XML requis</span><span class="sxs-lookup"><span data-stu-id="5ac5f-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="5ac5f-237">pour le type de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-237">for Data Type</span></span>|<span data-ttu-id="5ac5f-238">Attribut(s) XML facultatif(s)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="5ac5f-239">pour le type de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="5ac5f-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="5ac5f-241">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-241">None.</span></span>|  
|<span data-ttu-id="5ac5f-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="5ac5f-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="5ac5f-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="5ac5f-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="5ac5f-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-245">COLLATION</span></span>|  
|<span data-ttu-id="5ac5f-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="5ac5f-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-247">COLLATION</span></span>|  
|<span data-ttu-id="5ac5f-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="5ac5f-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="5ac5f-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="5ac5f-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="5ac5f-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="5ac5f-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="5ac5f-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="5ac5f-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="5ac5f-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="5ac5f-256">Pour plus d’informations sur les types de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><a name="AttrOfColumnElement"></a> <span data-ttu-id="5ac5f-257">Attributs de l'élément \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="5ac5f-257">Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="5ac5f-258">Cette section décrit les attributs de l’élément \<COLUMN>, qui sont récapitulés dans la syntaxe de schéma suivante :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="5ac5f-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="5ac5f-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="5ac5f-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="5ac5f-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="5ac5f-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="5ac5f-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="5ac5f-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="5ac5f-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="5ac5f-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="5ac5f-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="5ac5f-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="5ac5f-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="5ac5f-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="5ac5f-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="5ac5f-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="5ac5f-268">Un champ est mappé à une colonne dans la table cible à l'aide des attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="5ac5f-269">Attribut COLUMN</span><span class="sxs-lookup"><span data-stu-id="5ac5f-269">COLUMN Attribute</span></span>|<span data-ttu-id="5ac5f-270">Description</span><span class="sxs-lookup"><span data-stu-id="5ac5f-270">Description</span></span>|<span data-ttu-id="5ac5f-271">Facultatif /</span><span class="sxs-lookup"><span data-stu-id="5ac5f-271">Optional /</span></span><br /><br /> <span data-ttu-id="5ac5f-272">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="5ac5f-273">SOURCE **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="5ac5f-274">Spécifie l'ID du champ mappé à la colonne.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="5ac5f-275"><colonne source **= " *`fieldID`* "**/> correspond à <Field ID **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="5ac5f-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="5ac5f-276">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-276">Required</span></span>|  
|<span data-ttu-id="5ac5f-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="5ac5f-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="5ac5f-278">Spécifie le nom de la colonne dans l'ensemble de lignes représenté par le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="5ac5f-279">Ce nom de colonne est utilisé pour identifier la colonne dans le jeu de résultats, et il ne doit pas nécessairement correspondre au nom de colonne utilisé dans la table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="5ac5f-280">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-280">Required</span></span>|  
|<span data-ttu-id="5ac5f-281">xsi **:** type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="5ac5f-282">Il s'agit d'une construction XML (utilisée comme un attribut) qui identifie le type de données de l'instance de l'élément.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="5ac5f-283">La valeur de *ColumnType* détermine de quels attributs facultatifs (ci-dessous) vous avez besoin dans une instance donnée.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="5ac5f-284">Remarque : les valeurs possibles de *ColumnType* et leurs attributs associés sont répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="5ac5f-285">Facultatif</span><span class="sxs-lookup"><span data-stu-id="5ac5f-285">Optional</span></span>|  
|<span data-ttu-id="5ac5f-286">LONGUEUR **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="5ac5f-287">Définit la longueur d'une instance d'un type de données à longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="5ac5f-288">LENGTH est utilisé uniquement lorsque xsi:type est un type de données string.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="5ac5f-289">Cette valeur de *n* doit être un entier positif.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="5ac5f-290">Facultatif (disponible uniquement si xsi:type est un type de données string)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="5ac5f-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="5ac5f-292">Nombre de chiffres qui composent un nombre.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="5ac5f-293">Par exemple, le nombre 123,45 a une précision de 5.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="5ac5f-294">Cette valeur doit être un entier positif.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-294">The value must be a positive integer.</span></span>|<span data-ttu-id="5ac5f-295">Facultatif (disponible uniquement si xsi:type est un type de données variable-number)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="5ac5f-296">SCALE **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="5ac5f-297">Indique le nombre de chiffres à droite du point décimal (notre virgule) dans un nombre.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="5ac5f-298">Par exemple, le nombre 123,45 a une précision de 2.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="5ac5f-299">La valeur doit être un entier.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-299">The value must be an integer.</span></span>|<span data-ttu-id="5ac5f-300">Facultatif (disponible uniquement si xsi:type est un type de données variable-number)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="5ac5f-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="5ac5f-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="5ac5f-302">**"** NO **"** }</span></span>|<span data-ttu-id="5ac5f-303">Indique si une colonne peut prendre des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="5ac5f-304">Cet attribut est complètement indépendant de FIELDS.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="5ac5f-305">Cependant, si une colonne n'est pas NULLABLE et si le champ spécifie NULL (en ne spécifiant pas de valeur), une erreur d'exécution en résulte.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="5ac5f-306">L'attribut NULLABLE est utilisé uniquement si vous effectuez une instruction SELECT FROM OPENROWSET(BULK...) ordinaire.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="5ac5f-307">Facultatif (disponible pour n'importe quel type de données)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><a name="XsiTypeValuesOfCOLUMN"></a> <span data-ttu-id="5ac5f-308">Valeurs Xsi:type de l’élément \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="5ac5f-308">Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="5ac5f-309">La valeur xsi:type est une construction XML (utilisée comme un attribut) qui identifie le type de données d'une instance d'un élément.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="5ac5f-310">Pour plus d'informations sur l'utilisation de cette valeur, consultez « Placement de la valeur xsi:type dans un ensemble de données », plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="5ac5f-311">L’élément \<COLUMN> prend en charge les types de données SQL natifs, comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="5ac5f-312">Catégorie de type</span><span class="sxs-lookup"><span data-stu-id="5ac5f-312">Type Category</span></span>|<span data-ttu-id="5ac5f-313">Types de données \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="5ac5f-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="5ac5f-314">Attribut(s) XML requis</span><span class="sxs-lookup"><span data-stu-id="5ac5f-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="5ac5f-315">pour le type de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-315">for Data Type</span></span>|<span data-ttu-id="5ac5f-316">Attribut(s) XML facultatif(s)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="5ac5f-317">pour le type de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="5ac5f-318">Résolution</span><span class="sxs-lookup"><span data-stu-id="5ac5f-318">Fixed</span></span>|<span data-ttu-id="5ac5f-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT` et `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="5ac5f-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="5ac5f-320">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-320">None.</span></span>|<span data-ttu-id="5ac5f-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5ac5f-321">NULLABLE</span></span>|  
|<span data-ttu-id="5ac5f-322">Nombre variable</span><span class="sxs-lookup"><span data-stu-id="5ac5f-322">Variable Number</span></span>|<span data-ttu-id="5ac5f-323">`SQLDECIMAL` et `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="5ac5f-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="5ac5f-324">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-324">None.</span></span>|<span data-ttu-id="5ac5f-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="5ac5f-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="5ac5f-326">LOB</span><span class="sxs-lookup"><span data-stu-id="5ac5f-326">LOB</span></span>|<span data-ttu-id="5ac5f-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` et `SQLUDT`</span><span class="sxs-lookup"><span data-stu-id="5ac5f-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="5ac5f-328">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-328">None.</span></span>|<span data-ttu-id="5ac5f-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5ac5f-329">NULLABLE</span></span>|  
|<span data-ttu-id="5ac5f-330">LOB caractère</span><span class="sxs-lookup"><span data-stu-id="5ac5f-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="5ac5f-331">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-331">None.</span></span>|<span data-ttu-id="5ac5f-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="5ac5f-332">NULLABLE</span></span>|  
|<span data-ttu-id="5ac5f-333">Chaîne binaire</span><span class="sxs-lookup"><span data-stu-id="5ac5f-333">Binary string</span></span>|<span data-ttu-id="5ac5f-334">`SQLBINARY` et `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="5ac5f-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="5ac5f-335">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-335">None.</span></span>|<span data-ttu-id="5ac5f-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="5ac5f-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="5ac5f-337">Chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="5ac5f-337">Character string</span></span>|<span data-ttu-id="5ac5f-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` et `SQLNVARCHAR`</span><span class="sxs-lookup"><span data-stu-id="5ac5f-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="5ac5f-339">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-339">None.</span></span>|<span data-ttu-id="5ac5f-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="5ac5f-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ac5f-341">Pour exporter ou importer en bloc des données SQLXML, utilisez l'un des types de données ci-dessous dans votre fichier de format : SQLCHAR ou SQLVARYCHAR (les données sont envoyées dans la page de codes client ou dans la page de codes inhérente au classement) ; SQLNCHAR ou SQLNVARCHAR (les données sont envoyées au format Unicode) ; SQLBINARY ou SQLVARYBIN (les données sont envoyées sans être converties).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="5ac5f-342">Pour plus d’informations sur les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="5ac5f-343">Comment l’importation en bloc utilise l’élément \<ROW></span><span class="sxs-lookup"><span data-stu-id="5ac5f-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="5ac5f-344">L’élément \<ROW> est ignoré dans certains contextes.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="5ac5f-345">L’éventuelle incidence d’un élément \<ROW> sur une opération d’importation en bloc dépend du mode d’exécution de l’opération :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="5ac5f-346">Commande **bcp**</span><span class="sxs-lookup"><span data-stu-id="5ac5f-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="5ac5f-347">Quand des données sont chargées dans une table cible, **bcp** ignore le composant \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="5ac5f-348">**bcp** charge plutôt les données en fonction des types de colonnes de la table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="5ac5f-349">Instructions (fournisseur d’ensembles de lignes BULK INSERT et OPENROWSET)</span><span class="sxs-lookup"><span data-stu-id="5ac5f-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="5ac5f-350">Lors de l’importation en bloc de données dans une table, les instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] utilisent le composant \<ROW> pour générer l’ensemble de lignes d’entrée.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="5ac5f-351">En outre, les instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] effectuent les conversions de type appropriées en fonction des types de colonnes spécifiés sous \<ROW> et de la colonne correspondante dans la table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="5ac5f-352">Si une discordance existe entre les types de colonnes spécifiés dans le fichier de format et dans la table cible, une conversion de type supplémentaire intervient.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="5ac5f-353">Cette conversion de type supplémentaire peut entraîner certaines différences (c’est-à-dire, une perte de précision) dans le comportement du fournisseur d’ensembles de lignes en bloc BULK INSERT ou OPENROWSET en comparaison de **bcp**.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="5ac5f-354">Les informations de l’élément \<ROW> permettent de construire une ligne sans nécessiter d’informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="5ac5f-355">Pour cette raison, vous pouvez générer un ensemble de lignes en utilisant l’instruction SELECT (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5ac5f-356">La clause OPENROWSET BULK nécessite un fichier de format (notez que la conversion du type de données du champ au type de données d'une colonne n'est possible qu'avec un fichier de format XML).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="5ac5f-357">Comment l’importation en bloc utilise l’élément \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="5ac5f-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="5ac5f-358">Pour l’importation en bloc de données dans une table, les éléments \<COLUMN> dans un fichier de format mappent un champ de fichier de données à des colonnes de table en spécifiant les points suivants :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="5ac5f-359">La position de chaque champ dans une ligne du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="5ac5f-360">Le type de colonne, qui est utilisé pour convertir le type de données du champ au type de données de la colonne souhaitée.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="5ac5f-361">Si aucune colonne n'est mappée à un champ, le champ n'est pas copié dans la ou les lignes générées.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="5ac5f-362">Ce comportement permet à un fichier de données de générer des lignes avec différentes colonnes (dans différentes tables).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="5ac5f-363">De même, pour l’exportation en bloc de données à partir d’une table, chaque élément \<COLUMN> du fichier de format mappe la colonne de la ligne de la table d’entrée à son champ correspondant du fichier de données de sortie.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="5ac5f-364">Placement de la valeur xsi:type dans un ensemble de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="5ac5f-365">Lorsqu'un document XML est validé à travers le langage XSD (XML Schema Definition), la valeur xsi:type n'est pas placée dans l'ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="5ac5f-366">Cependant, vous pouvez placer les informations xsi:type dans l'ensemble de données en chargeant le fichier de format XML dans un document XML (par exemple, `myDoc`), tel qu'illustré dans l'extrait de code suivant :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="5ac5f-367">Exemples de fichiers de format XML</span><span class="sxs-lookup"><span data-stu-id="5ac5f-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="5ac5f-368">Cette section contient des informations sur l'utilisation de fichiers de format XML dans différents cas de figure, avec un exemple [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ac5f-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-369">Dans les fichiers de données illustrés dans les exemples ci-dessous, `<tab>` indique un caractère de tabulation et `<return>` , un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-370">Pour plus d’informations sur la création de fichiers de format, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="5ac5f-371">A.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-371">A.</span></span> <span data-ttu-id="5ac5f-372">Classement de champs de données caractères dans le même ordre que les colonnes d'une table</span><span class="sxs-lookup"><span data-stu-id="5ac5f-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="5ac5f-373">L'exemple suivant illustre un fichier de format XML décrivant un fichier de données qui contient trois champs de données caractères.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="5ac5f-374">Le fichier de format mappe le fichier de données sur une table contenant trois colonnes.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="5ac5f-375">Les champs de données correspondent un-à-un aux colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="5ac5f-376">**Table (ligne) :** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="5ac5f-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="5ac5f-377">**Fichier de données (enregistrement) :** Age\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="5ac5f-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="5ac5f-378">Le fichier de format XML suivant lit les données du fichier de données et les écrit dans la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="5ac5f-379">Dans l'élément `<RECORD>` , le fichier de format représente les valeurs de données de chacun des trois champs au format caractère.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="5ac5f-380">Pour chaque champ, l'attribut `TERMINATOR` indique le terminateur qui suit la valeur de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="5ac5f-381">Les champs de données correspondent un-à-un aux colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="5ac5f-382">Dans l'élément `<ROW>` , le fichier de format mappe la colonne `Age` au premier champ, la colonne `FirstName` au deuxième et la colonne `LastName` au troisième.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-383">Pour obtenir un exemple [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] équivalent, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="5ac5f-384">B.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-384">B.</span></span> <span data-ttu-id="5ac5f-385">Classement de champs de données et de colonnes d'une table dans un ordre différent</span><span class="sxs-lookup"><span data-stu-id="5ac5f-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="5ac5f-386">L'exemple suivant illustre un fichier de format XML décrivant un fichier de données qui contient trois champs de données caractères.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="5ac5f-387">Le fichier de format mappe le fichier de données sur une table contenant trois colonnes classées dans un ordre différent de celui des champs du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="5ac5f-388">**Table (ligne) :** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="5ac5f-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="5ac5f-389">**Fichier de données** (enregistrement) : Age\<tab>Lastname\<tab>Firstname\<return></span><span class="sxs-lookup"><span data-stu-id="5ac5f-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="5ac5f-390">Dans l'élément `<RECORD>` , le fichier de format représente les valeurs de données de chacun des trois champs au format caractère.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="5ac5f-391">Dans l'élément `<ROW>` , le fichier de format mappe la colonne `Age` au premier champ, la colonne `FirstName` au troisième et la colonne `LastName` au second.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-392">Pour obtenir un exemple [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] équivalent, consultez [Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="5ac5f-393">C.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-393">C.</span></span> <span data-ttu-id="5ac5f-394">Omission d'un champ de données</span><span class="sxs-lookup"><span data-stu-id="5ac5f-394">Omitting a data field</span></span>  
 <span data-ttu-id="5ac5f-395">L'exemple suivant illustre un fichier de format XML décrivant un fichier de données qui contient quatre champs de données caractères.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="5ac5f-396">Le fichier de format mappe le fichier de données sur une table contenant trois colonnes.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="5ac5f-397">Le deuxième champ de données ne correspond à aucune colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="5ac5f-398">**Table (ligne) :** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span><span class="sxs-lookup"><span data-stu-id="5ac5f-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="5ac5f-399">**Fichier de données (enregistrement) :** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="5ac5f-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="5ac5f-400">Dans l'élément `<RECORD>` , le fichier de format représente les valeurs de données de chacun des quatre champs au format caractère.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="5ac5f-401">Pour chaque champ, l'attribut TERMINATOR indique le terminateur qui suit la valeur de données.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="5ac5f-402">Dans l'élément `<ROW>` , le fichier de format mappe la colonne `Age` au premier champ, la colonne `FirstName` au troisième et la colonne `LastName` au quatrième.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5ac5f-403">Pour obtenir un exemple [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] équivalent, consultez [Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ac5f-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="5ac5f-404">D.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-404">D.</span></span> <span data-ttu-id="5ac5f-405">Mappage de xsi:type \<FIELD> à xsi:type \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="5ac5f-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="5ac5f-406">L'exemple suivant illustre différents types de champs et leurs mappages sur des colonnes.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="5ac5f-407">E.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-407">E.</span></span> <span data-ttu-id="5ac5f-408">Mappage de données XML sur une table</span><span class="sxs-lookup"><span data-stu-id="5ac5f-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="5ac5f-409">Dans l'exemple ci-dessous, une table (`t_xml`) vide à deux colonnes est créée : sa première colonne est mappée sur le type de données `int` et la seconde, sur le type de données `xml` .</span><span class="sxs-lookup"><span data-stu-id="5ac5f-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="5ac5f-410">Le fichier de format XML suivant charge un fichier de données dans la table `t_xml`.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="5ac5f-411">F.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-411">F.</span></span> <span data-ttu-id="5ac5f-412">Importation de champs à longueur fixe ou à largeur fixe</span><span class="sxs-lookup"><span data-stu-id="5ac5f-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="5ac5f-413">L'exemple suivant décrit des champs fixes de `10` ou `6` caractères chacun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="5ac5f-414">Le fichier de format représente ces longueurs-largeurs de champ sous la forme de `LENGTH="10"` et `LENGTH="6"`, respectivement.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="5ac5f-415">Chaque ligne des fichiers de données se termine par une combinaison retour chariot/saut de ligne, {CR}{LF}, représentée par le fichier de format sous la forme `TERMINATOR="\r\n"`.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="5ac5f-416">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="5ac5f-416">Additional Examples</span></span>  
 <span data-ttu-id="5ac5f-417">Les rubriques suivantes contiennent des exemples supplémentaires de fichiers de format non XML et de fichiers de format XML :</span><span class="sxs-lookup"><span data-stu-id="5ac5f-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5ac5f-418">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-419">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-420">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5ac5f-421">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5ac5f-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5ac5f-422">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-423">Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-424">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-425">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="5ac5f-426">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="5ac5f-427">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5ac5f-427">Related Content</span></span>  
 <span data-ttu-id="5ac5f-428">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ac5f-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac5f-429">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ac5f-429">See Also</span></span>  
 <span data-ttu-id="5ac5f-430">[Importation et exportation en bloc de données &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5ac5f-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="5ac5f-431">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ac5f-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="5ac5f-432">[Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5ac5f-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="5ac5f-433">Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac5f-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
