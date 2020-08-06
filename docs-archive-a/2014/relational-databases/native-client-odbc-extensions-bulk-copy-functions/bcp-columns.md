---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698159"
---
# <a name="bcp_columns"></a><span data-ttu-id="cfc92-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="cfc92-102">bcp_columns</span></span>
  <span data-ttu-id="cfc92-103">Définit le nombre total de colonnes trouvées dans le fichier utilisateur pour une utilisation avec une copie en bloc vers ou depuis [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfc92-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cfc92-104">[bcp_setbulkmode](bcp-setbulkmode.md) peut être utilisé à la place de bcp_columns et [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="cfc92-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc92-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cfc92-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cfc92-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="cfc92-106">Arguments</span></span>  
 <span data-ttu-id="cfc92-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cfc92-107">*hdbc*</span></span>  
 <span data-ttu-id="cfc92-108">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="cfc92-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="cfc92-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="cfc92-109">*nColumns*</span></span>  
 <span data-ttu-id="cfc92-110">Nombre total de colonnes dans le fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cfc92-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="cfc92-111">Même si vous vous préparez à copier en bloc des données à partir du fichier utilisateur vers une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table et que vous n’envisagez pas de copier toutes les colonnes dans le fichier utilisateur, vous devez toujours définir *nColumns* sur le nombre total de colonnes de fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cfc92-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cfc92-112">Retours</span><span class="sxs-lookup"><span data-stu-id="cfc92-112">Returns</span></span>  
 <span data-ttu-id="cfc92-113">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="cfc92-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfc92-114">Notes</span><span class="sxs-lookup"><span data-stu-id="cfc92-114">Remarks</span></span>  
 <span data-ttu-id="cfc92-115">Cette fonction ne peut être appelée qu’une fois que [bcp_init](bcp-init.md) a été appelé avec un nom de fichier valide.</span><span class="sxs-lookup"><span data-stu-id="cfc92-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="cfc92-116">Vous devez appeler cette fonction uniquement si vous envisagez d'utiliser un format de fichier utilisateur qui diffère du format par défaut.</span><span class="sxs-lookup"><span data-stu-id="cfc92-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="cfc92-117">Pour plus d’informations sur une description du format de fichier utilisateur par défaut, consultez **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="cfc92-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="cfc92-118">Après avoir appelé `bcp_columns` , vous devez appeler [bcp_colfmt](bcp-colfmt.md)pour chaque colonne dans le fichier utilisateur afin de définir complètement un format de fichier personnalisé.</span><span class="sxs-lookup"><span data-stu-id="cfc92-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc92-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfc92-119">See Also</span></span>  
 [<span data-ttu-id="cfc92-120">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cfc92-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
