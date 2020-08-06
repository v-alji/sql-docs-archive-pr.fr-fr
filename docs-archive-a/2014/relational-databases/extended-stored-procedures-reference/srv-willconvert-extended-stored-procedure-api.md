---
title: srv_willconvert (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709472"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="d7613-102">srv_willconvert (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="d7613-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d7613-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="d7613-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d7613-104">Détermine si une conversion de type de données spécifique est disponible au sein de la bibliothèque ODS.</span><span class="sxs-lookup"><span data-stu-id="d7613-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7613-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d7613-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7613-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d7613-106">Arguments</span></span>  
 <span data-ttu-id="d7613-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="d7613-107">*srctype*</span></span>  
 <span data-ttu-id="d7613-108">Indique le type de données des données à convertir.</span><span class="sxs-lookup"><span data-stu-id="d7613-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="d7613-109">Ce paramètre peut être n'importe lequel des types de données des API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="d7613-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="d7613-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="d7613-110">*desttype*</span></span>  
 <span data-ttu-id="d7613-111">Indique le type de données vers lequel les données sources sont converties.</span><span class="sxs-lookup"><span data-stu-id="d7613-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="d7613-112">Ce paramètre peut être n'importe lequel des types de données des API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="d7613-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d7613-113">Retours</span><span class="sxs-lookup"><span data-stu-id="d7613-113">Returns</span></span>  
 <span data-ttu-id="d7613-114">TRUE si la conversion de type de données est prise en charge ; FALSE, dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="d7613-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7613-115">Notes</span><span class="sxs-lookup"><span data-stu-id="d7613-115">Remarks</span></span>  
 <span data-ttu-id="d7613-116">Pour obtenir une description de chaque type de données, consultez [Types de données &#40;API de procédure stockée étendue&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="d7613-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7613-117">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="d7613-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d7613-118">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d7613-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7613-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7613-119">See Also</span></span>  
 [<span data-ttu-id="d7613-120">srv_convert &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="d7613-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
