---
title: Ajouter un lien hypertexte à une URL (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697547"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="a44e2-102">Ajouter un lien hypertexte à une URL (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a44e2-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a44e2-103">Vous pouvez ajouter un lien hypertexte à un élément de rapport lorsque vous souhaitez que les utilisateurs soient en mesure de cliquer sur un lien dans un rapport et d'ouvrir un navigateur vers l'URL que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="a44e2-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="a44e2-104">Un lien hypertexte peut être une URL statique ou une expression qui est évaluée en une URL.</span><span class="sxs-lookup"><span data-stu-id="a44e2-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="a44e2-105">Si une base de données comprend un champ avec des URL, vous pouvez insérer ce champ dans l'expression de façon à produire une liste dynamique de liens hypertexte dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="a44e2-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="a44e2-106">Vous pouvez ajouter des liens hypertexte aux zones de texte, aux images, aux graphiques et aux jauges.</span><span class="sxs-lookup"><span data-stu-id="a44e2-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="a44e2-107">Vous devez vous assurer que l'utilisateur a accès à l'URL que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="a44e2-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="a44e2-108">Vous pouvez également spécifier des URL vers des rapports sur n'importe quel serveur de rapports que vos utilisateurs et vous-même avez l'autorisation d'afficher en utilisant des demandes d'URL dirigées vers le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a44e2-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="a44e2-109">Par exemple, vous pouvez spécifier un rapport et masquer l'explorateur de documents à l'utilisateur lorsqu'il affiche pour la première fois le rapport.</span><span class="sxs-lookup"><span data-stu-id="a44e2-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="a44e2-110">Pour plus d’informations, consultez [Accès URL &#40;SSRS&#41;](../url-access-ssrs.md) dans la [documentation de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a44e2-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="a44e2-111">Vous pouvez ajouter un lien hypertexte à une URL vers tout élément qui a une propriété **Action** , par exemple une zone de texte, une image ou une série calculée dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="a44e2-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="a44e2-112">Lorsque l'utilisateur clique sur l'élément de rapport en question, l'action que vous définissez est exécutée.</span><span class="sxs-lookup"><span data-stu-id="a44e2-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="a44e2-113">Pour plus d’informations, consultez [Boîte de dialogue Propriétés relatives aux actions &#40;Générateur de rapports et SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) et [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a44e2-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a44e2-114">Pour une prise en main rapide, consultez [Didacticiel : mettre en forme du texte &#40;Générateur de rapports&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a44e2-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a44e2-115">Les liens qui sont associés à des champs de dataset peuvent être vulnérables à des opérations de falsification à des fins malveillantes.</span><span class="sxs-lookup"><span data-stu-id="a44e2-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="a44e2-116">Pour plus d’informations, consultez [Sécuriser des rapports et des ressources](../security/secure-reports-and-resources.md) dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][documentation en ligne](https://go.microsoft.com/fwlink/?LinkId=154888) sur msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a44e2-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="a44e2-117">Pour ajouter un lien hypertexte</span><span class="sxs-lookup"><span data-stu-id="a44e2-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="a44e2-118">En mode Création de rapport, cliquez avec le bouton droit sur la zone de texte, l’image ou le graphique auquel vous voulez ajouter un lien, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a44e2-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a44e2-119">Dans la boîte de dialogue Propriétés, cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="a44e2-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="a44e2-120">Sélectionnez **Atteindre l'URL**.</span><span class="sxs-lookup"><span data-stu-id="a44e2-120">Select **Go to URL**.</span></span> <span data-ttu-id="a44e2-121">Une section supplémentaire apparaît dans la boîte de dialogue pour cette option.</span><span class="sxs-lookup"><span data-stu-id="a44e2-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="a44e2-122">Dans **Sélectionner une URL**, entrez ou sélectionnez une URL ou une expression qui prend la valeur d’une URL, ou cliquez sur la flèche déroulante et cliquez sur le nom d’un champ qui contient une URL.</span><span class="sxs-lookup"><span data-stu-id="a44e2-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="a44e2-123">(Facultatif) Le texte n'est pas mis en forme automatiquement en tant que lien.</span><span class="sxs-lookup"><span data-stu-id="a44e2-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="a44e2-124">Pour le texte, il est utile de modifier la couleur et l'effet du texte pour indiquer qu'il s'agit d'un lien.</span><span class="sxs-lookup"><span data-stu-id="a44e2-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="a44e2-125">Par exemple, changez la couleur en bleu et l'effet en soulignement dans la section **Police** sous l'onglet Accueil du ruban.</span><span class="sxs-lookup"><span data-stu-id="a44e2-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="a44e2-126">Pour tester le lien, cliquez sur **Exécuter** afin d'afficher l'aperçu du rapport, puis cliquez sur l'élément de rapport sur lequel vous avez défini ce lien.</span><span class="sxs-lookup"><span data-stu-id="a44e2-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44e2-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a44e2-127">See Also</span></span>  
 <span data-ttu-id="a44e2-128">[Tri interactif, explorateurs de documents et liens &#40;Générateur de rapports et SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a44e2-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a44e2-129">Créer un explorateur de documents &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a44e2-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
