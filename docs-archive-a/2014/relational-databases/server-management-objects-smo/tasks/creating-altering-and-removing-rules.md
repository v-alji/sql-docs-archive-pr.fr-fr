---
title: Création, modification et suppression de règles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612211"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="7a258-102">Création, modification et suppression de règles</span><span class="sxs-lookup"><span data-stu-id="7a258-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="7a258-103">Dans SMO, les règles sont représentées par l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule>.</span><span class="sxs-lookup"><span data-stu-id="7a258-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="7a258-104">La règle est définie par la propriété <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>, qui est une chaîne de texte contenant une expression de condition qui utilise des opérateurs ou des prédicats, par exemple IN, LIKE ou BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="7a258-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="7a258-105">Elle ne peut pas faire référence à des colonnes ou à d'autres objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="7a258-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="7a258-106">Vous pouvez y inclure des fonctions intégrées qui ne font pas référence à des objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="7a258-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="7a258-107">La définition dans la propriété <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> doit contenir une variable qui fait référence à la valeur de données entrée.</span><span class="sxs-lookup"><span data-stu-id="7a258-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="7a258-108">Vous pouvez utiliser n’importe quel nom ou symbole pour représenter la valeur lors de la création de la règle, mais le premier caractère doit être le \@ symbole.</span><span class="sxs-lookup"><span data-stu-id="7a258-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a258-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="7a258-109">Example</span></span>  
 <span data-ttu-id="7a258-110">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="7a258-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="7a258-111">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7a258-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="7a258-112">Création, modification et suppression d'une règle en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a258-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="7a258-113">Cet exemple de code montre comment créer une règle, l'attacher à une colonne, modifier des propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule>, la détacher de la colonne, puis la supprimer.</span><span class="sxs-lookup"><span data-stu-id="7a258-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7a258-114">L'instruction `Dim` pour l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule> est spécifiée avec le chemin d'accès complet de l'assembly pour éviter toute ambiguïté avec un objet <xref:Microsoft.SqlServer.Management.Smo.Rule> de l'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="7a258-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="7a258-115">Création, modification et suppression d'une règle en Visual C#</span><span class="sxs-lookup"><span data-stu-id="7a258-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="7a258-116">Cet exemple de code montre comment créer une règle, l'attacher à une colonne, modifier des propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule>, la détacher de la colonne, puis la supprimer.</span><span class="sxs-lookup"><span data-stu-id="7a258-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7a258-117">L'instruction `Dim` pour l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule> est spécifiée avec le chemin d'accès complet de l'assembly pour éviter toute ambiguïté avec un objet <xref:Microsoft.SqlServer.Management.Smo.Rule> de l'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="7a258-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="7a258-118">Création, modification et suppression d'une règle dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a258-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="7a258-119">Cet exemple de code montre comment créer une règle, l'attacher à une colonne, modifier des propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule>, la détacher de la colonne, puis la supprimer.</span><span class="sxs-lookup"><span data-stu-id="7a258-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7a258-120">L'instruction `Dim` pour l'objet <xref:Microsoft.SqlServer.Management.Smo.Rule> est spécifiée avec le chemin d'accès complet de l'assembly pour éviter toute ambiguïté avec un objet <xref:Microsoft.SqlServer.Management.Smo.Rule> de l'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="7a258-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a258-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a258-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
