---
title: Modifier les propriétés avancées du service SQL Server à l’aide de VBScript | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614411"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="1bff2-102">Modifier les propriétés avancées du service SQL Server à l'aide de VBScript</span><span class="sxs-lookup"><span data-stu-id="1bff2-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="1bff2-103">Cette section décrit comment créer un programme VBScript qui répertorie la version des instances installées de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui s’exécutent sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1bff2-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="1bff2-104">L'exemple de code répertorie les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui s'exécutent sur l'ordinateur et leur version.</span><span class="sxs-lookup"><span data-stu-id="1bff2-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="1bff2-105">Liste des noms et versions des instances installées de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bff2-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="1bff2-106">Ouvrez un nouveau document dans un éditeur de texte, tel que le Bloc-notes [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bff2-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="1bff2-107">Copiez le code qui suit cette procédure et enregistrez le fichier avec une extension .vbs.</span><span class="sxs-lookup"><span data-stu-id="1bff2-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="1bff2-108">Cet exemple est appelé test.vbs.</span><span class="sxs-lookup"><span data-stu-id="1bff2-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="1bff2-109">Connectez-vous à une instance du fournisseur WMI pour Gestion de l'ordinateur avec la fonction VBScript `GetObject`.</span><span class="sxs-lookup"><span data-stu-id="1bff2-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="1bff2-110">Cet exemple se connecte à un ordinateur distant nommé mpc, mais omet le nom d'ordinateur pour se connecter à l'ordinateur local : winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="1bff2-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="1bff2-111">Pour plus d'informations sur la fonction `GetObject`, consultez les informations de référence sur VBScript.</span><span class="sxs-lookup"><span data-stu-id="1bff2-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="1bff2-112">Utilisez la méthode `InstancesOf` pour dresser la liste des services.</span><span class="sxs-lookup"><span data-stu-id="1bff2-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="1bff2-113">Ces services peuvent également être énumérés à l'aide d'une requête WQL simple et d'une méthode `ExecQuery` à la place d'une méthode `InstancesOf`.</span><span class="sxs-lookup"><span data-stu-id="1bff2-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="1bff2-114">Utilisez la méthode `ExecQuery` et une requête WQL pour extraire le nom et la version des instances installées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bff2-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="1bff2-115">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="1bff2-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="1bff2-116">Exécutez le script en tapant `cscript test.vbs` à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="1bff2-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bff2-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="1bff2-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
