---
title: Ajouter des extraits de code Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603917"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="ab8fd-102">Ajouter des extraits de code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab8fd-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="ab8fd-103">Vous pouvez ajouter vos propres extraits de code Transact-SQL au jeu d'extraits de code prédéfinis inclus dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="ab8fd-104">Création d'un fichier d'extrait de code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab8fd-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="ab8fd-105">La première partie de la création d'un extrait de code [!INCLUDE[tsql](../../includes/tsql-md.md)] consiste à créer un fichier XML contenant le texte de votre extrait de code.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="ab8fd-106">Le fichier doit avoir une extension de fichier .snippet et satisfaire à la configuration requise du [schéma d'extrait de code](https://go.microsoft.com/fwlink/?LinkId=207504).</span><span class="sxs-lookup"><span data-stu-id="ab8fd-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="ab8fd-107">Définissez le langage de l'extrait de code sur SQL.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="ab8fd-108">Vous pouvez utiliser les extraits de code prédéfinis fournis avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme exemples.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="ab8fd-109">Pour rechercher les extraits de code prédéfinis, ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sélectionnez le menu **Outils** et cliquez sur **Gestionnaire des extraits de code**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="ab8fd-110">Sélectionnez **SQL** dans la zone de liste **Langage** ; le chemin d'accès aux extraits de code [!INCLUDE[tsql](../../includes/tsql-md.md)] s'affiche dans la zone **Emplacement** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="ab8fd-111">Enregistrement de l'extrait de code</span><span class="sxs-lookup"><span data-stu-id="ab8fd-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="ab8fd-112">Après avoir créé le fichier d'extrait de code, utilisez le Gestionnaire des extraits de code pour enregistrer l'extrait de code dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ab8fd-113">Vous pouvez ajouter un dossier qui contient plusieurs extraits de code ou importer des extraits de code individuels vers le dossier **Mes extraits de code** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ab8fd-114">Procédures</span><span class="sxs-lookup"><span data-stu-id="ab8fd-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="ab8fd-115">Ajout d'un dossier d'extrait de code</span><span class="sxs-lookup"><span data-stu-id="ab8fd-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="ab8fd-116">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab8fd-117">Sélectionnez le menu **Outils** et cliquez sur **Gestionnaire des extraits de code**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="ab8fd-118">Cliquez sur le bouton **Add** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="ab8fd-119">Accédez au dossier qui contient vos extraits de code et cliquez sur le bouton **Sélectionner un dossier** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="ab8fd-120">Importation d'un extrait de code</span><span class="sxs-lookup"><span data-stu-id="ab8fd-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="ab8fd-121">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab8fd-122">Sélectionnez le menu **Outils** et cliquez sur **Gestionnaire des extraits de code**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="ab8fd-123">Cliquez sur le bouton **Import**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="ab8fd-124">Accédez au dossier qui contient votre extrait de code, cliquez sur le fichier .snippet, puis cliquez sur le bouton **Ouvrir** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ab8fd-125">Exemples</span><span class="sxs-lookup"><span data-stu-id="ab8fd-125">Examples</span></span>  
 <span data-ttu-id="ab8fd-126">L'exemple suivant crée un extrait de code d'entourage `TRY-CATCH` et l'importe vers [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="ab8fd-127">Collez le code suivant dans le bloc-notes, puis enregistrez-le sous le fichier TryCatch.snippet.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="ab8fd-128">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab8fd-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="ab8fd-129">Sélectionnez le menu **Outils** et cliquez sur **Gestionnaire des extraits de code**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="ab8fd-130">Cliquez sur le bouton **Import**.</span><span class="sxs-lookup"><span data-stu-id="ab8fd-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="ab8fd-131">Accédez au dossier qui contient TryCatch.snippet, cliquez sur le fichier TryCatch.snippet, puis cliquez sur le bouton **Ouvrir** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="ab8fd-132">Vous ne devez pas avoir d'extrait de code TryCatch dans votre dossier **Mes extraits de code** .</span><span class="sxs-lookup"><span data-stu-id="ab8fd-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8fd-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab8fd-133">See Also</span></span>  
 [<span data-ttu-id="ab8fd-134">Insérer des extraits de code d’entourage (surround-with) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab8fd-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
