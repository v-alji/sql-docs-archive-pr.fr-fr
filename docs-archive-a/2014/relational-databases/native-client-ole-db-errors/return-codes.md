---
title: Codes de retour | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612794"
---
# <a name="return-codes"></a><span data-ttu-id="75e2e-102">Codes de retour</span><span class="sxs-lookup"><span data-stu-id="75e2e-102">Return Codes</span></span>
  <span data-ttu-id="75e2e-103">Au niveau le plus élémentaire, une fonction membre réussit ou échoue.</span><span class="sxs-lookup"><span data-stu-id="75e2e-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="75e2e-104">À un niveau plus précis, une fonction peut réussir, mais son succès peut ne pas être ce que le développeur d'applications prévoyait.</span><span class="sxs-lookup"><span data-stu-id="75e2e-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="75e2e-105">Pour plus d’informations sur les codes de retour OLE DB, consultez [Codes de retour (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="75e2e-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="75e2e-106">Quand une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonction membre du fournisseur OLE DB Native Client retourne S_OK, la fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="75e2e-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="75e2e-107">Quand une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonction membre du fournisseur OLE DB Native Client ne retourne pas S_OK, le DÉCOMPRESSION HRESULT OLE/com a échoué et les macros IS_ERROR peuvent déterminer le succès ou l’échec global d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="75e2e-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="75e2e-108">En cas d’échec ou si IS_ERROR retourne la valeur TRUE, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client est assuré que l’exécution de la fonction membre a échoué.</span><span class="sxs-lookup"><span data-stu-id="75e2e-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="75e2e-109">En cas d’échec ou de IS_ERROR retournent la valeur FALSe et HRESULT n’est pas égal à S_OK, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client est assuré que la fonction a réussi d’une certaine manière.</span><span class="sxs-lookup"><span data-stu-id="75e2e-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="75e2e-110">Le consommateur peut récupérer des informations détaillées sur ce retour de « réussite avec informations » à partir des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces d’erreur du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="75e2e-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="75e2e-111">En outre, dans le cas où une fonction échoue clairement (la macro ayant échoué retourne la valeur TRUE), les informations d’erreur étendues sont disponibles à partir des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces d’erreur du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="75e2e-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="75e2e-112">Les consommateurs de fournisseurs OLE DB Native Client rencontrent généralement le retour HRESULT DB_S_ERRORSOCCURRED « réussite avec les informations ».</span><span class="sxs-lookup"><span data-stu-id="75e2e-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="75e2e-113">En général, les fonctions membres qui retournent DB_S_ERRORSOCCURRED définissent un ou plusieurs paramètres qui remettent les valeurs d'état au consommateur.</span><span class="sxs-lookup"><span data-stu-id="75e2e-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="75e2e-114">Comme aucune information d'erreur ne peut être disponible au consommateur autre que celle retournée dans les paramètres état-valeur, les consommateurs doivent implémenter la logique d'application pour extraire les valeurs d'état lorsqu'elles sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="75e2e-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="75e2e-115">Les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctions membres du fournisseur OLE DB Native Client ne retournent pas le code de réussite S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="75e2e-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="75e2e-116">Toutes les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctions membres du fournisseur Native Client OLE DB retournent toujours S_OK pour indiquer la réussite.</span><span class="sxs-lookup"><span data-stu-id="75e2e-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e2e-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75e2e-117">See Also</span></span>  
 [<span data-ttu-id="75e2e-118">Erreurs</span><span class="sxs-lookup"><span data-stu-id="75e2e-118">Errors</span></span>](errors.md)  
  
  
