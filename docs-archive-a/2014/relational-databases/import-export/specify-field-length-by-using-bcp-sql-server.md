---
title: Spécifier la longueur des champs au moyen de bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696843"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="5f553-102">Spécifier la longueur des champs au moyen de bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f553-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="5f553-103">La longueur de champ indique le nombre maximal de caractères nécessaires pour représenter les données au format caractères.</span><span class="sxs-lookup"><span data-stu-id="5f553-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="5f553-104">La longueur de champ est déjà connue si les données sont enregistrées au format natif. Par exemple, les données de type `int` occupent 4 octets.</span><span class="sxs-lookup"><span data-stu-id="5f553-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="5f553-105">Si vous avez indiqué 0 comme longueur de préfixe, la commande **BCP** vous demande la longueur du champ, les longueurs de champ par défaut et l’impact de la longueur de champ sur le stockage des données dans les fichiers de données qui contiennent des `char` données.</span><span class="sxs-lookup"><span data-stu-id="5f553-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="5f553-106">Invite bcp pour la longueur des champs</span><span class="sxs-lookup"><span data-stu-id="5f553-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="5f553-107">Si une commande **bcp** interactive contient l’option **in** ou **out** sans commutateur de fichier de format ( **-f**) ou sans commutateur de format de données ( **-n**, **-c**, **-w** ou **-N**), la commande demande la longueur de champ de chaque champ de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="5f553-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="5f553-108">Pour obtenir un exemple illustrant cette invite en contexte, consultez [Spécifier des formats de données pour la compatibilité lors de l’utilisation de bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f553-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f553-109">Après avoir indiqué de façon interactive tous les champs d’une commande **bcp**, cette dernière vous demande de sauvegarder vos réponses dans un fichier de format autre que XML pour chacun des champs fournis.</span><span class="sxs-lookup"><span data-stu-id="5f553-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="5f553-110">Pour plus d’informations sur les fichiers de format non-XML, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f553-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="5f553-111">Plusieurs facteurs déterminent si une commande **bcp** vous demande la longueur de champ :</span><span class="sxs-lookup"><span data-stu-id="5f553-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="5f553-112">Lorsque vous copiez des types de données dont la longueur n’est pas fixe et que vous spécifiez une longueur de préfixe nulle (0), la commande **bcp** demande la longueur de champ.</span><span class="sxs-lookup"><span data-stu-id="5f553-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="5f553-113">Lors de la conversion de données non caractères en données caractères, la commande **bcp** suggère une longueur de champ par défaut suffisamment importante pour stocker les données.</span><span class="sxs-lookup"><span data-stu-id="5f553-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="5f553-114">Si le type de stockage de fichier est non caractère, la commande **bcp** ne demande pas de longueur de champ.</span><span class="sxs-lookup"><span data-stu-id="5f553-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="5f553-115">Les données sont stockées dans la représentation de données native de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (format natif).</span><span class="sxs-lookup"><span data-stu-id="5f553-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="5f553-116">Utilisation des longueurs de champs par défaut</span><span class="sxs-lookup"><span data-stu-id="5f553-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="5f553-117">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommande généralement d’accepter les valeurs par défaut de longueur de champ suggérées par la commande **bcp**.</span><span class="sxs-lookup"><span data-stu-id="5f553-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="5f553-118">Lors de la création d'un fichier de données en mode caractère, l'utilisation de la longueur de champ par défaut garantit que les données ne sont pas tronquées et que des erreurs de dépassement de capacité numérique ne se produiront pas.</span><span class="sxs-lookup"><span data-stu-id="5f553-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="5f553-119">Des problèmes peuvent se produire si vous spécifiez une longueur de champ incorrecte.</span><span class="sxs-lookup"><span data-stu-id="5f553-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="5f553-120">Par exemple, si cous copiez des données numériques et si vous spécifiez une longueur de champ trop faible pour ces données, l'utilitaire **bcp** affiche un message de dépassement de capacité et ne copie pas les données.</span><span class="sxs-lookup"><span data-stu-id="5f553-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="5f553-121">En outre, si vous exportez des `datetime` données et que vous spécifiez une longueur de champ inférieure à 26 octets pour la chaîne de caractères, l’utilitaire **BCP** tronque les données sans message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="5f553-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5f553-122">Lorsque vous utilisez l'option de taille par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'attend à lire une chaîne complète.</span><span class="sxs-lookup"><span data-stu-id="5f553-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="5f553-123">Dans certains cas, l'utilisation de la longueur de champ par défaut peut entraîner l'erreur « Fin de fichier inattendue ».</span><span class="sxs-lookup"><span data-stu-id="5f553-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="5f553-124">En règle générale, cette erreur se produit avec les `money` `datetime` types de données et lorsque seule une partie du champ attendu se trouve dans le fichier de données ; par exemple, lorsqu’une `datetime` valeur de *mm* / *JJ* / *AA* est spécifiée sans le composant heure et qu’elle est, par conséquent, inférieure à la longueur de 24 caractères attendue d’une `datetime` valeur au `char` format.</span><span class="sxs-lookup"><span data-stu-id="5f553-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="5f553-125">Pour éviter ce type d'erreur, utilisez des marques de fin de champ ou des champs de données de longueur fixe, ou modifiez la longueur par défaut du champ en spécifiant une autre valeur.</span><span class="sxs-lookup"><span data-stu-id="5f553-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="5f553-126">Longueur par défaut des champs pour le stockage de fichiers au format caractère</span><span class="sxs-lookup"><span data-stu-id="5f553-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="5f553-127">Le tableau ci-dessous répertorie les longueurs par défaut des champs à enregistrer dans des fichiers de type caractère.</span><span class="sxs-lookup"><span data-stu-id="5f553-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="5f553-128">Les données pouvant être de type NULL sont de même longueur que les données de type non NULL.</span><span class="sxs-lookup"><span data-stu-id="5f553-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="5f553-129">Type de données</span><span class="sxs-lookup"><span data-stu-id="5f553-129">Data type</span></span>|<span data-ttu-id="5f553-130">Longueur par défaut (en caractères)</span><span class="sxs-lookup"><span data-stu-id="5f553-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="5f553-131">Longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="5f553-132">Longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="5f553-133">Le double de la longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="5f553-134">Le double de la longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="5f553-135">0</span><span class="sxs-lookup"><span data-stu-id="5f553-135">0</span></span>|  
|`ntext`|<span data-ttu-id="5f553-136">0</span><span class="sxs-lookup"><span data-stu-id="5f553-136">0</span></span>|  
|`bit`|<span data-ttu-id="5f553-137">1</span><span class="sxs-lookup"><span data-stu-id="5f553-137">1</span></span>|  
|`binary`|<span data-ttu-id="5f553-138">Le double de la longueur définie pour la colonne + 1</span><span class="sxs-lookup"><span data-stu-id="5f553-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="5f553-139">Le double de la longueur définie pour la colonne + 1</span><span class="sxs-lookup"><span data-stu-id="5f553-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="5f553-140">0</span><span class="sxs-lookup"><span data-stu-id="5f553-140">0</span></span>|  
|`datetime`|<span data-ttu-id="5f553-141">24</span><span class="sxs-lookup"><span data-stu-id="5f553-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="5f553-142">24</span><span class="sxs-lookup"><span data-stu-id="5f553-142">24</span></span>|  
|`float`|<span data-ttu-id="5f553-143">30</span><span class="sxs-lookup"><span data-stu-id="5f553-143">30</span></span>|  
|`real`|<span data-ttu-id="5f553-144">30</span><span class="sxs-lookup"><span data-stu-id="5f553-144">30</span></span>|  
|`int`|<span data-ttu-id="5f553-145">12</span><span class="sxs-lookup"><span data-stu-id="5f553-145">12</span></span>|  
|`bigint`|<span data-ttu-id="5f553-146">19</span><span class="sxs-lookup"><span data-stu-id="5f553-146">19</span></span>|  
|`smallint`|<span data-ttu-id="5f553-147">7</span><span class="sxs-lookup"><span data-stu-id="5f553-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="5f553-148">5</span><span class="sxs-lookup"><span data-stu-id="5f553-148">5</span></span>|  
|`money`|<span data-ttu-id="5f553-149">30</span><span class="sxs-lookup"><span data-stu-id="5f553-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="5f553-150">30</span><span class="sxs-lookup"><span data-stu-id="5f553-150">30</span></span>|  
|`decimal`|<span data-ttu-id="5f553-151">41\*</span><span class="sxs-lookup"><span data-stu-id="5f553-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="5f553-152">41\*</span><span class="sxs-lookup"><span data-stu-id="5f553-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="5f553-153">37</span><span class="sxs-lookup"><span data-stu-id="5f553-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="5f553-154">17</span><span class="sxs-lookup"><span data-stu-id="5f553-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="5f553-155">0</span><span class="sxs-lookup"><span data-stu-id="5f553-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="5f553-156">0</span><span class="sxs-lookup"><span data-stu-id="5f553-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="5f553-157">0</span><span class="sxs-lookup"><span data-stu-id="5f553-157">0</span></span>|  
|<span data-ttu-id="5f553-158">UDT</span><span class="sxs-lookup"><span data-stu-id="5f553-158">UDT</span></span>|<span data-ttu-id="5f553-159">Longueur de la colonne d'un terme défini par l'utilisateur (UDT)</span><span class="sxs-lookup"><span data-stu-id="5f553-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="5f553-160">XML</span><span class="sxs-lookup"><span data-stu-id="5f553-160">XML</span></span>|<span data-ttu-id="5f553-161">0</span><span class="sxs-lookup"><span data-stu-id="5f553-161">0</span></span>|  
  
 <span data-ttu-id="5f553-162">\*Pour plus d’informations sur `decimal` les `numeric` types de données et, consultez [decimal et numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f553-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f553-163">Une colonne de type `tinyint` peut posséder des valeurs comprises entre 0 et 255. Le nombre maximal de caractères nécessaires à la représentation de tout nombre compris dans cet intervalle est de trois (représentant les valeurs comprises entre 100 et 255).</span><span class="sxs-lookup"><span data-stu-id="5f553-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="5f553-164">Longueur par défaut des champs pour le stockage de fichiers au format natif</span><span class="sxs-lookup"><span data-stu-id="5f553-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="5f553-165">Le tableau ci-dessous répertorie les longueurs par défaut des champs à enregistrer dans des fichiers au format natif.</span><span class="sxs-lookup"><span data-stu-id="5f553-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="5f553-166">Les données pouvant être de type NULL sont de même longueur que les données de type non NULL. Les données de type caractère sont toujours enregistrées au format caractère.</span><span class="sxs-lookup"><span data-stu-id="5f553-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="5f553-167">Type de données</span><span class="sxs-lookup"><span data-stu-id="5f553-167">Data type</span></span>|<span data-ttu-id="5f553-168">Longueur par défaut (en caractères)</span><span class="sxs-lookup"><span data-stu-id="5f553-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="5f553-169">1</span><span class="sxs-lookup"><span data-stu-id="5f553-169">1</span></span>|  
|`binary`|<span data-ttu-id="5f553-170">Longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="5f553-171">Longueur définie pour la colonne</span><span class="sxs-lookup"><span data-stu-id="5f553-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="5f553-172">0</span><span class="sxs-lookup"><span data-stu-id="5f553-172">0</span></span>|  
|`datetime`|<span data-ttu-id="5f553-173">8</span><span class="sxs-lookup"><span data-stu-id="5f553-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="5f553-174">4</span><span class="sxs-lookup"><span data-stu-id="5f553-174">4</span></span>|  
|`float`|<span data-ttu-id="5f553-175">8</span><span class="sxs-lookup"><span data-stu-id="5f553-175">8</span></span>|  
|`real`|<span data-ttu-id="5f553-176">4</span><span class="sxs-lookup"><span data-stu-id="5f553-176">4</span></span>|  
|`int`|<span data-ttu-id="5f553-177">4</span><span class="sxs-lookup"><span data-stu-id="5f553-177">4</span></span>|  
|`bigint`|<span data-ttu-id="5f553-178">8</span><span class="sxs-lookup"><span data-stu-id="5f553-178">8</span></span>|  
|`smallint`|<span data-ttu-id="5f553-179">2</span><span class="sxs-lookup"><span data-stu-id="5f553-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="5f553-180">1</span><span class="sxs-lookup"><span data-stu-id="5f553-180">1</span></span>|  
|`money`|<span data-ttu-id="5f553-181">8</span><span class="sxs-lookup"><span data-stu-id="5f553-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="5f553-182">4</span><span class="sxs-lookup"><span data-stu-id="5f553-182">4</span></span>|  
|<span data-ttu-id="5f553-183">`decimal`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5f553-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="5f553-184">`numeric`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5f553-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="5f553-185">16</span><span class="sxs-lookup"><span data-stu-id="5f553-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="5f553-186">8</span><span class="sxs-lookup"><span data-stu-id="5f553-186">8</span></span>|  
  
 <span data-ttu-id="5f553-187"><sup>1</sup> pour plus d’informations sur `decimal` les `numeric` types de données et, consultez [Decimal et numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f553-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="5f553-188">Dans tous les cas précédents, pour créer un fichier de données pour un chargement ultérieur dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et faire en sorte que l'espace de stockage soit minimal, utilisez un préfixe de longueur avec le type de stockage de fichier et la longueur du champ par défaut.</span><span class="sxs-lookup"><span data-stu-id="5f553-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f553-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f553-189">See Also</span></span>  
 <span data-ttu-id="5f553-190">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5f553-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="5f553-191">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5f553-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="5f553-192">[Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f553-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="5f553-193">[Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f553-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="5f553-194">[Spécifier le type de stockage de fichiers à l’aide de bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f553-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="5f553-195">Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l’importation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f553-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
