---
title: Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano czynności konfiguracyjne, które należy wykonać, aby można było wprowadzać i importować dane zewnętrzne do prognoz przepływów pieniężnych.
author: rcarlson
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 66bdb8bd638859bb4fc5565e3f12a8f671addcff
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186697"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="e0dd1-103">Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e0dd1-104">Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="e0dd1-105">W tym temacie opisano czynności konfiguracyjne właściwe dla korzystania z danych zewnętrznych, które umożliwiają uwzględnienie danych zewnętrznych w prognozie przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="e0dd1-106">Ustawienia danych zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="e0dd1-106">External data setup</span></span>

<span data-ttu-id="e0dd1-107">Karta **Źródło zewnętrzne** na stronie **Ustawienia prognozy przepływów pieniężnych** (**Zarządzanie gotówką i bankami \> Prognozowanie przepływów pieniężnych**) służy do wprowadzania ustawień, które pozwalają na używanie danych zewnętrznych w prognozach przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="e0dd1-108">Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Prognozowanie przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).</span><span class="sxs-lookup"><span data-stu-id="e0dd1-108">For more information about the setup, see [Cash flow forecasting](../cash-bank-management/cash-flow-forecasting.md).</span></span>

<span data-ttu-id="e0dd1-109">Aby wprowadzić dane zewnętrzne dla prognoz przepływów pieniężnych, można skorzystać z funkcji Otwórz w programie Excel służącej do wprowadzania i modyfikowania danych zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="e0dd1-110">Wybierz przycisk **Dane zewnętrzne**, a następnie wybierz opcję **Dodaj dane zewnętrzne** lub **Edytuj istniejące dane zewnętrzne**.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="e0dd1-111">Po otwarciu pliku programu Microsoft Excel można wprowadzić informacje w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="e0dd1-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="e0dd1-112">**Identyfikator wpisu**</span><span class="sxs-lookup"><span data-stu-id="e0dd1-112">**Entry ID**</span></span>
- <span data-ttu-id="e0dd1-113">**Opis** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-113">**Description** (optional)</span></span>
- <span data-ttu-id="e0dd1-114">**Nazwa źródła zewnętrznego** — wybierz jedną z wartości z listy zdefiniowanej podczas konfigurowania modułu Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="e0dd1-115">**Osoba prawna**</span><span class="sxs-lookup"><span data-stu-id="e0dd1-115">**Legal Entity**</span></span>
- <span data-ttu-id="e0dd1-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="e0dd1-116">**Date**</span></span>
- <span data-ttu-id="e0dd1-117">**Kwota w walucie transakcji**</span><span class="sxs-lookup"><span data-stu-id="e0dd1-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="e0dd1-118">**Kod waluty**</span><span class="sxs-lookup"><span data-stu-id="e0dd1-118">**Currency Code**</span></span>
- <span data-ttu-id="e0dd1-119">**Wymiar domyślny** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="e0dd1-120">**Numer dokumentu** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-120">**Document number** (optional)</span></span>
- <span data-ttu-id="e0dd1-121">**Numer konta** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-121">**Account number** (optional)</span></span>
- <span data-ttu-id="e0dd1-122">**Nazwa konta** (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e0dd1-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="e0dd1-123">Importowanie danych zewnętrznych przy użyciu struktury zarządzania danymi</span><span class="sxs-lookup"><span data-stu-id="e0dd1-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="e0dd1-124">Dane zewnętrzne dla prognoz przepływów pieniężnych można importować za pomocą obszaru roboczego **Zarządzanie danymi** i jednostki o nazwie **Wprowadzanie z zewnętrznego źródła dla prognozy przepływów pieniężnych**.</span><span class="sxs-lookup"><span data-stu-id="e0dd1-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="e0dd1-125">Ponadto jeśli trzeba przenieść dane konfiguracyjne z jednego środowiska do drugiego, dostępne są następujące jednostki dla wymaganych tabel konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="e0dd1-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="e0dd1-126">Konfiguracja zewnętrznego źródła prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="e0dd1-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="e0dd1-127">Konfiguracja firmy zewnętrznego źródła prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="e0dd1-127">Cash flow forecast external source legal entity setup</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
