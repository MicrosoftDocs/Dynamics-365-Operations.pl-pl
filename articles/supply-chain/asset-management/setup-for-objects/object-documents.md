---
title: Dokumenty składnika majątku
description: W tym temacie objaśniono dokumenty w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783505"
---
# <a name="asset-documents"></a><span data-ttu-id="cfbb7-103">Dokumenty składnika majątku</span><span class="sxs-lookup"><span data-stu-id="cfbb7-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="cfbb7-104">W tym temacie objaśniono dokumenty w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="cfbb7-105">W module Zarządzanie składnikami majątku można skonfigurować dokumenty w taki sposób, aby były one automatycznie powiązane na przykład z typami zadań, producentami składników majątku, typami składników majątku lub składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="cfbb7-106">Ta funkcja jest przydatna, kiedy zwalniane są zaktualizowane wersje dokumentów.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="cfbb7-107">W takim przypadku wystarczy umieścić zaktualizowany dokument w standardowej lokalizacji, której używasz dla dokumentów Microsoft Dynamics 365 for Finance and Operations, i dołączyć dokument do utworzonego rekordu dokumentu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-107">In that case, you just have to put the updated document in the standard location that you use for your Microsoft Dynamics 365 for Finance and Operations documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="cfbb7-108">Do zaktualizowanego dokument można następnie uzyskać dostęp z menu **Wszystkie składniki majątku**, **Aktywne składniki majątku**, **Moje aktywne składniki majątku**, **Wszystkie zlecenia pracy** oraz **Aktywne zadania zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="cfbb7-109">Proces dołączania dokumentów do rekordu dokumentu zasobów używa standardowego systemu obsługi dokumentów w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-109">The process for attaching documents to an asset document record uses the standard document handling system in Finance and Operations.</span></span>

<span data-ttu-id="cfbb7-110">**Przykład 1:** dokument, który jest powiązany z typem zadania może opisywać procedurę dla tego typu zadania.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="cfbb7-111">**Przykład 2:** dokument powiązany z kombinacją typu składnika majątku, producenta i modelu może być standardowym podręcznikiem dla wybranego modelu producenta składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="cfbb7-112">Tworzenie relacji dokumentu składnika majątku</span><span class="sxs-lookup"><span data-stu-id="cfbb7-112">Create asset document relation</span></span>

1. <span data-ttu-id="cfbb7-113">Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Dokumenty składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="cfbb7-114">Wybierz **Nowy**, aby utworzyć rekord dokumentu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="cfbb7-115">W zależności od tego, jak szczegółowa ma być relacja dokumentu, dokonaj odpowiednich selekcji w jednym lub kilku z następujących pól: **Typ składnika majątku**, **Producent**, **Model**, **Składnik majątku**, **Kategoria typy zadania**, **Typ zadania**, **Wariant typu zadania** oraz **Kryterium doboru**</span><span class="sxs-lookup"><span data-stu-id="cfbb7-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="cfbb7-116">Opcje, które są dostępne w polach **Wariant typu zadania** i **Kryterium doboru** zależą od opcji wybranych w polu **Typ zadania**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfbb7-117">Gdy system wyszukuje dokumenty, które powinny być powiązane ze składnikami majątku lub zleceniem pracy, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy dokumentu składnika majątku w celu sprawdzenia możliwego dopasowania.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="cfbb7-118">W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="cfbb7-119">Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Kryterium doboru**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="cfbb7-120">Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="cfbb7-121">Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Typ zadania** itd.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="cfbb7-122">Jak widać w układzie strony **Dokumenty składnika majątku** to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="cfbb7-123">Kilka dokumentów może być związanych ze składnikiem majątku lub zleceniem pracy.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="cfbb7-124">Zależnie od potrzeb można edytować poziom usługi na żądaniu konserwacji lub zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="cfbb7-125">Wybierz **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-125">Select **Attachments**.</span></span> <span data-ttu-id="cfbb7-126">W programie Finance and Operations zostanie wyświetlona strona **Obsługa dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-126">The standard **Document handling** page in Finance and Operations appears.</span></span>
5. <span data-ttu-id="cfbb7-127">Skonfiguruj dokumenty lub notatki, które powinny być dołączone do rekordu dokumentu składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="cfbb7-128">Po dołączeniu dokumentów w polu **Załączniki** pokazuje się liczba dokumentów powiązanych z rekordem.</span><span class="sxs-lookup"><span data-stu-id="cfbb7-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
