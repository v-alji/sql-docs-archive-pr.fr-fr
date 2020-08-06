---
title: Exécuter des fichiers de script Transact-SQL à l'aide de sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602036"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="bb6ff-102">Exécuter des fichiers de script Transact-SQL à l'aide de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="bb6ff-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="bb6ff-103">Vous pouvez utiliser `sqlcmd` pour exécuter un fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb6ff-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="bb6ff-104">Un fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] est un fichier texte qui contient une combinaison d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)], de commandes `sqlcmd` et de variables de script.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="bb6ff-105">Pour créer un fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] simple à l'aide du Bloc-notes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bb6ff-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="bb6ff-106">Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, sur **Accessoires**, puis cliquez sur **Bloc-notes**.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="bb6ff-107">Copiez et collez le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans le Bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="bb6ff-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="bb6ff-108">Enregistrez le fichier sous **myScript.sql** sur le lecteur C.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="bb6ff-109">Pour exécuter le fichier de script</span><span class="sxs-lookup"><span data-stu-id="bb6ff-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="bb6ff-110">Ouvrez une fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="bb6ff-111">Dans la fenêtre d’invite de commandes, entrez ce qui suit : `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="bb6ff-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="bb6ff-112">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="bb6ff-113">La liste des noms et des adresses des employés de la société [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] apparaît dans la fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="bb6ff-114">Pour enregistrer ce résultat dans un fichier texte</span><span class="sxs-lookup"><span data-stu-id="bb6ff-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="bb6ff-115">Ouvrez une fenêtre d’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="bb6ff-116">Dans la fenêtre d’invite de commandes, entrez ce qui suit : `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="bb6ff-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="bb6ff-117">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="bb6ff-118">Aucun résultat n'est retourné dans la fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="bb6ff-119">Le résultat est au contraire envoyé dans le fichier EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="bb6ff-120">Vous pouvez vérifier ce résultat en ouvrant le fichier EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="bb6ff-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6ff-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb6ff-121">See Also</span></span>  
 <span data-ttu-id="bb6ff-122">[Démarrer l’utilitaire sqlcmd](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="bb6ff-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="bb6ff-123">Utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="bb6ff-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
