---
title: Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano czynności konfiguracyjne, które należy wykonać, aby można było wprowadzać i importować dane zewnętrzne do prognoz przepływów pieniężnych.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae0eba6d397725cf425d9781a597d904e1958d44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009400"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="12f34-103">Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="12f34-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="12f34-104">Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="12f34-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="12f34-105">W tym temacie opisano czynności konfiguracyjne właściwe dla korzystania z danych zewnętrznych, które umożliwiają uwzględnienie danych zewnętrznych w prognozie przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="12f34-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="12f34-106">Ustawienia danych zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="12f34-106">External data setup</span></span>

<span data-ttu-id="12f34-107">Karta **Źródło zewnętrzne** na stronie **Ustawienia prognozy przepływów pieniężnych** (**Zarządzanie gotówką i bankami \> Prognozowanie przepływów pieniężnych**) służy do wprowadzania ustawień, które pozwalają na używanie danych zewnętrznych w prognozach przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="12f34-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="12f34-108">Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Prognozowanie przepływów pieniężnych](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="12f34-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="12f34-109">Aby wprowadzić dane zewnętrzne dla prognoz przepływów pieniężnych, można skorzystać z funkcji Otwórz w programie Excel służącej do wprowadzania i modyfikowania danych zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="12f34-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="12f34-110">Wybierz przycisk **Dane zewnętrzne**, a następnie wybierz opcję **Dodaj dane zewnętrzne** lub **Edytuj istniejące dane zewnętrzne**.</span><span class="sxs-lookup"><span data-stu-id="12f34-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="12f34-111">Po otwarciu pliku programu Microsoft Excel można wprowadzić informacje w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="12f34-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="12f34-112">**Identyfikator wpisu**</span><span class="sxs-lookup"><span data-stu-id="12f34-112">**Entry ID**</span></span>
- <span data-ttu-id="12f34-113">**Opis** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="12f34-113">**Description** (optional)</span></span>
- <span data-ttu-id="12f34-114">**Nazwa źródła zewnętrznego** — wybierz jedną z wartości z listy zdefiniowanej podczas konfigurowania modułu Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="12f34-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="12f34-115">**Osoba prawna**</span><span class="sxs-lookup"><span data-stu-id="12f34-115">**Legal Entity**</span></span>
- <span data-ttu-id="12f34-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="12f34-116">**Date**</span></span>
- <span data-ttu-id="12f34-117">**Kwota w walucie transakcji**</span><span class="sxs-lookup"><span data-stu-id="12f34-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="12f34-118">**Kod waluty**</span><span class="sxs-lookup"><span data-stu-id="12f34-118">**Currency Code**</span></span>
- <span data-ttu-id="12f34-119">**Wymiar domyślny** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="12f34-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="12f34-120">**Numer dokumentu** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="12f34-120">**Document number** (optional)</span></span>
- <span data-ttu-id="12f34-121">**Numer konta** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="12f34-121">**Account number** (optional)</span></span>
- <span data-ttu-id="12f34-122">**Nazwa konta** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="12f34-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="12f34-123">Importowanie danych zewnętrznych przy użyciu struktury zarządzania danymi</span><span class="sxs-lookup"><span data-stu-id="12f34-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="12f34-124">Dane zewnętrzne dla prognoz przepływów pieniężnych można importować za pomocą obszaru roboczego **Zarządzanie danymi** i jednostki o nazwie **Wprowadzanie z zewnętrznego źródła dla prognozy przepływów pieniężnych**.</span><span class="sxs-lookup"><span data-stu-id="12f34-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="12f34-125">Ponadto jeśli trzeba przenieść dane konfiguracyjne z jednego środowiska do drugiego, dostępne są następujące jednostki dla wymaganych tabel konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="12f34-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="12f34-126">Konfiguracja zewnętrznego źródła prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="12f34-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="12f34-127">Konfiguracja firmy zewnętrznego źródła prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="12f34-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="12f34-128">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="12f34-128">Privacy notice</span></span>
<span data-ttu-id="12f34-129">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="12f34-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
