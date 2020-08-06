---
title: Composants de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611033"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="8276b-102">Composants de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8276b-102">Components of SQL Server Native Client</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="8276b-103">Native Client contient les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="8276b-103">Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="8276b-104">Composant</span><span class="sxs-lookup"><span data-stu-id="8276b-104">Component</span></span>|<span data-ttu-id="8276b-105">Description</span><span class="sxs-lookup"><span data-stu-id="8276b-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8276b-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="8276b-106">sqlncli11.dll</span></span>|<span data-ttu-id="8276b-107">Fichier DDL (Dynamic-Link Library) contenant l'ensemble des fonctionnalités [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="8276b-108">Sont inclus le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client et le pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="8276b-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="8276b-109">sqlnclir11.rll</span></span>|<span data-ttu-id="8276b-110">Fichier de ressources d'accompagnement pour la bibliothèque [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="8276b-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="8276b-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="8276b-112">Fichier d'aide de l'Assistant Source de données qui explique comment créer une source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ou du fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="8276b-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="8276b-113">sqlncli.h</span></span>|<span data-ttu-id="8276b-114">En-tête de fichier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client contenant toutes les nouvelles définitions nécessaires pour pouvoir utiliser [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="8276b-115">Ce fichier d'en-tête remplace les fichiers odbcss.h et sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="8276b-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="8276b-116">**Remarque :**  Vous ne pouvez pas référencer sqlncli. h et odbcss. h dans le même programme, mais vous pouvez faire référence à sqlncli. h et SQLOLEDB. h dans le même programme tant que sqloledb. h est défini en premier.</span><span class="sxs-lookup"><span data-stu-id="8276b-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="8276b-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="8276b-117">sqlncli11.lib</span></span>|<span data-ttu-id="8276b-118">Fichier de bibliothèque nécessaire pour appeler directement les fonctions de l’utilitaire **BCP** qui font partie du [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="8276b-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="8276b-119">**Remarque :**  Si vous référencez le fichier SQLNCLI11. lib dans votre code de programmation, vous devez vous assurer que le fichier sqlncli11.dll se trouve dans votre chemin d’accès système et dans le chemin d’accès système des utilisateurs qui utilisent votre application.</span><span class="sxs-lookup"><span data-stu-id="8276b-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8276b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8276b-120">See Also</span></span>  
 [<span data-ttu-id="8276b-121">Génération d’applications avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8276b-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
