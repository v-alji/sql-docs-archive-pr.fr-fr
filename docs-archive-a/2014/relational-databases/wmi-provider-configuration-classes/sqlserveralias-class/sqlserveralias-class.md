---
title: SqlServerAlias, classe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614424"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="47896-102">Classe SqlServerAlias</span><span class="sxs-lookup"><span data-stu-id="47896-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="47896-103">La [classe SqlServerAlias](sqlserveralias-class.md) représente un alias de connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="47896-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="47896-104">Un alias de connexion au serveur est requis lorsque les deux conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="47896-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="47896-105">Le client se connecte à une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur un transport réseau qui n’est pas le transport réseau par défaut.</span><span class="sxs-lookup"><span data-stu-id="47896-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="47896-106">l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à laquelle le client est connecté écoute sur un autre canal nommé.</span><span class="sxs-lookup"><span data-stu-id="47896-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="47896-107">**Remarque :** La [classe SqlServerAlias](sqlserveralias-class.md) hérite `Put` de la méthode de la classe Provider.</span><span class="sxs-lookup"><span data-stu-id="47896-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="47896-108">Toutefois, elle ne retourne pas de résultats comme indiqué par la méthode `Provider::Put`.</span><span class="sxs-lookup"><span data-stu-id="47896-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="47896-109">Pour plus d'informations, consultez la documentation relative à WMI.</span><span class="sxs-lookup"><span data-stu-id="47896-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47896-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47896-110">See Also</span></span>  
 [<span data-ttu-id="47896-111">Configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="47896-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
