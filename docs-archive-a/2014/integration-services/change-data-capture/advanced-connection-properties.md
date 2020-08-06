---
title: Propriétés avancées de connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8dc844d1fdfb1e82f0ffa8de93a6a1060ef190cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611938"
---
# <a name="advanced-connection-properties"></a><span data-ttu-id="685e0-102">Propriétés avancées de connexion</span><span class="sxs-lookup"><span data-stu-id="685e0-102">Advanced Connection Properties</span></span>
  <span data-ttu-id="685e0-103">Pour ajouter des paramètres de connexion à la chaîne de connexion, utilisez la boîte de dialogue **Propriétés avancées de connexion** .</span><span class="sxs-lookup"><span data-stu-id="685e0-103">Use the **Advanced Connection Properties** dialog box to add more connection parameters to the connection string.</span></span>  
  
 <span data-ttu-id="685e0-104">Les paramètres de connexion supplémentaires peuvent être des paramètres de connexion ODBC pris en charge par l'instance de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="685e0-104">The additional connection parameters can be any ODBC connection parameter that is supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database instance you are using.</span></span>  
  
 <span data-ttu-id="685e0-105">Les paramètres ajoutés à partir de la boîte de dialogue **Propriétés avancées de connexion** sont ajoutés aux paramètres sélectionnés dans la boîte de dialogue **Connexion à SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="685e0-105">The parameters added using the **Advanced Connection Properties** dialog box are added to the parameters selected in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="685e0-106">La dernière instance de chaque paramètre fourni remplace toutes les instances précédentes du paramètre.</span><span class="sxs-lookup"><span data-stu-id="685e0-106">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="685e0-107">Les paramètres ajoutés à partir de la boîte de dialogue **Paramètres de connexion avancés** suivent et remplacent les paramètres fournis dans la boîte de dialogue **Connexion SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="685e0-107">Parameters added using the **Advanced Connection Parameters** dialog box follow and replace the parameters provided in the **SQL Server Connection** dialog box.</span></span> <span data-ttu-id="685e0-108">Par exemple, si la boîte de dialogue **Connexion SQL Server** spécifie SERVEUR1 en tant que Nom du serveur et si la page **Paramètres de connexion supplémentaires** indique ;SERVEUR=SERVEUR2, la connexion sera établie à SERVEUR2.</span><span class="sxs-lookup"><span data-stu-id="685e0-108">For example, if the **SQL Server Connection** dialog box specifies SERVER1 as the Server name, and the **Additional Connection Parameters** page contains ;SERVER=SERVER2, the connection will be made to SERVER2.</span></span>  
  
 <span data-ttu-id="685e0-109">Les paramètres ajoutés à partir de la boîte de dialogue **Propriétés avancées de connexion** sont transmis sous forme de texte brut.</span><span class="sxs-lookup"><span data-stu-id="685e0-109">Parameters added using the **Advanced Connection Properties** dialog box are passed as plain text.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="685e0-110">N'incluez pas les informations d'identification de connexion dans la boîte de dialogue **Propriétés avancées de connexion** .</span><span class="sxs-lookup"><span data-stu-id="685e0-110">Do not include login credentials in the **Advanced Connection Properties** dialog box.</span></span> <span data-ttu-id="685e0-111">Ceux-ci ne seront pas chiffrés lorsqu'ils seront transmis sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="685e0-111">They will not be encrypted when they are passed across the network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685e0-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="685e0-112">See Also</span></span>  
 <span data-ttu-id="685e0-113">[Accéder à la console du concepteur CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="685e0-113">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="685e0-114">Connexion SQL Server pour la création d’une instance</span><span class="sxs-lookup"><span data-stu-id="685e0-114">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
