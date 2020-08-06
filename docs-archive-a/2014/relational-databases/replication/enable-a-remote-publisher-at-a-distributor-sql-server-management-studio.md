---
title: Activer un serveur de publication distant sur un serveur de distribution (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601356"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="3832c-102">activer un serveur de publication distant sur un serveur de distribution (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3832c-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3832c-103">Activer un serveur de publication afin d'utiliser un serveur de distribution distant sur la page **Serveurs de publication** .</span><span class="sxs-lookup"><span data-stu-id="3832c-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="3832c-104">Cette page est disponible dans l’Assistant Configuration de la distribution et la boîte de dialogue **Propriétés du serveur de distribution - \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="3832c-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="3832c-105">Pour plus d’informations sur l’utilisation de l’Assistant et l’accès à la boîte de dialogue, consultez [Configurer la publication et la distribution](configure-publishing-and-distribution.md) et [Afficher et modifier les propriétés du serveur de distribution et du serveur de publication](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3832c-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="3832c-106">Pour activer un serveur de publication dans l'Assistant Configuration de distribution</span><span class="sxs-lookup"><span data-stu-id="3832c-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="3832c-107">Sur la page **Serveurs de publication** de l'Assistant Configuration de publication, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3832c-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="3832c-108">Cliquez sur **Ajouter un serveur de publication SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3832c-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="3832c-109">Pour plus d'informations sur l'activation d'un serveur de publication Oracle pour utiliser un serveur de distribution, consultez [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="3832c-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="3832c-110">Dans la boîte de dialogue **Se connecter au serveur** , indiquez les informations de connexion du serveur de publication qui utilisera le serveur de distribution distant, plus cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="3832c-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="3832c-111">Sur la page **Mot de passe du serveur de distribution** , dans les zones de texte **Mot de passe** et **Confirmer le mot de passe** , spécifiez un mot de passe fort pour le compte **distributor_admin** que la réplication utilise pour se connecter du serveur de publication sur le serveur de distribution afin d'effectuer des tâches administratives.</span><span class="sxs-lookup"><span data-stu-id="3832c-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="3832c-112">Pour afficher et modifier les paramètres d’un serveur de publication, cliquez sur le bouton des propriétés ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="3832c-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="3832c-113">Pour activer un serveur de publication dans la boîte de dialogue Propriétés du serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="3832c-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="3832c-114">Dans la page **Serveurs de publication** de la boîte de dialogue **Propriétés du serveur de distribution - \<Distributor>** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3832c-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="3832c-115">Cliquez sur **Ajouter un serveur de publication SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3832c-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="3832c-116">Pour plus d'informations sur l'activation d'un serveur de publication Oracle pour utiliser un serveur de distribution, consultez [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="3832c-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="3832c-117">Dans la boîte de dialogue **Se connecter au serveur** , indiquez les informations de connexion du serveur de publication qui utilisera le serveur de distribution distant, plus cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="3832c-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="3832c-118">Sur la page **Serveurs de publication** , dans les zones de texte **Mot de passe** et **Confirmer le mot de passe** , spécifiez un mot de passe fort pour le compte **distributor_admin** que la réplication utilise pour se connecter du serveur de publication sur le serveur de distribution afin d'effectuer des tâches administratives.</span><span class="sxs-lookup"><span data-stu-id="3832c-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="3832c-119">Pour afficher et modifier les paramètres d’un serveur de publication, cliquez sur le bouton des propriétés ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="3832c-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3832c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3832c-120">See Also</span></span>  
 <span data-ttu-id="3832c-121">[Configurer la publication et la distribution](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="3832c-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="3832c-122">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="3832c-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="3832c-123">Sécuriser le serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="3832c-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
