---
title: Wyświetlanie wyników automatyzacji faktur od dostawców (wersja zapoznawcza)
description: W tym temacie opisano sposób wyświetlania stanu faktur od dostawców w zautomatyzowanym procesie przesyłania do przepływu pracy.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3b87af4c64f8021a1b23cca5d8f38ac21c8efbd4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248102"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="0a16b-103">Wyświetlanie wyników automatyzacji faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="0a16b-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a16b-104">W tym temacie opisano sposób wyświetlania stanu faktur od dostawców w zautomatyzowanym procesie przesyłania do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="0a16b-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="0a16b-105">Szczegóły historii automatyzacji są obsługiwane dla każdej importowanej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0a16b-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="0a16b-106">W zależności od wykonywanych przez użytkownika procesów biznesowych na stronie **Oczekujące faktury od dostawcy** jest wyświetlana wartość **Stan automatycznego dopasowania odbioru** i **Automatyczne przesyłanie do stanu przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="0a16b-107">Istnieje możliwość wyświetlenia szczegółów i utworzenia planu skoncentrowanego na fakturach, które nie wykonały zautomatyzowanego kroku.</span><span class="sxs-lookup"><span data-stu-id="0a16b-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="0a16b-108">Po rozwiązaniu tego problemu można wznowić proces zautomatyzowany dla importowanej faktury.</span><span class="sxs-lookup"><span data-stu-id="0a16b-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="0a16b-109">Aby można było edytować przesłaną fakturę, należy wstrzymać automatyczne przetwarzanie.</span><span class="sxs-lookup"><span data-stu-id="0a16b-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="0a16b-110">Jeśli faktura w procesie zautomatyzowanego przesyłania do przepływu pracy musi zostać wstrzymana, należy w polu **Uwzględnij w zautomatyzowanym przetwarzaniu** ustaw wartość **Nie** na stronie **Faktury od dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="0a16b-111">Automatyzacja nie zostanie uruchamiana, dopóki w polu **Przetwarzanie automatyczne** nie zostanie ustawiona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="0a16b-112">Dalszą automatyzację faktury można wstrzymać, jeśli jeszcze nie znajduje się w systemie przepływu pracy i nie jest używana przez proces zautomatyzowany.</span><span class="sxs-lookup"><span data-stu-id="0a16b-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="0a16b-113">Jeśli zaimportowana faktura podlega procesowi przesyłania do przepływu pracy”, można wyświetlić wartość **Stan automatyzacji** na stronie **Faktury od dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="0a16b-114">Śledzone są następujące stany:</span><span class="sxs-lookup"><span data-stu-id="0a16b-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="0a16b-115">**Uwzględnione** — zautomatyzowane procesy zdefiniowane na stronie **Parametry rozrachunków z dostawcami** działają poprawnie, ale nie zostały jeszcze ukończone.</span><span class="sxs-lookup"><span data-stu-id="0a16b-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="0a16b-116">**Wstrzymane** — wykonywane są zautomatyzowane procesy zdefiniowane na stronie **Parametry rozrachunków z dostawcami**, ale co najmniej jeden krok w procesie nie powiódł się.</span><span class="sxs-lookup"><span data-stu-id="0a16b-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="0a16b-117">Stan **Wstrzymane** jest również stosowany, jeśli w polu **Uwzględnij w zautomatyzowanym przetwarzaniu** jest ustawiona wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="0a16b-118">Te błędy można wyświetlić, wybierając opcję **Wyświetl ostatnie wyniki**.</span><span class="sxs-lookup"><span data-stu-id="0a16b-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="0a16b-119">**W przepływie pracy** — zaimportowana faktura została przesłana do systemu przepływu pracy przez zautomatyzowany proces przesyłania do przepływu pracy lub ręcznie.</span><span class="sxs-lookup"><span data-stu-id="0a16b-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="0a16b-120">**Przepływ pracy ukończony** — ukończono proces przepływu pracy dla zaimportowanej faktury.</span><span class="sxs-lookup"><span data-stu-id="0a16b-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]