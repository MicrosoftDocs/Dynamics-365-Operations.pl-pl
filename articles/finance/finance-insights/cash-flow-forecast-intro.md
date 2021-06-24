---
title: Prognoza przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano możliwości prognozowania przepływów pieniężnych.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 64935db3b50e7598f2076ecbec72aba020d4f908
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186547"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="5948d-103">Prognoza przepływów pieniężnych (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="5948d-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5948d-104">Przepływy pieniężne mają podstawowe znaczenie dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="5948d-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="5948d-105">Nawet rentowne firmy mogą być niewypłacalne, jeśli nie utrzymują przepływu pieniężnego na poziomie zaspokajającym bieżące potrzeby.</span><span class="sxs-lookup"><span data-stu-id="5948d-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="5948d-106">Możliwość prognozowania przepływów pieniężnych w ramach Finance Insights może pomóc firmom w efektywnym monitorowaniu sald środków pieniężnych i zarządzaniu nimi.</span><span class="sxs-lookup"><span data-stu-id="5948d-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="5948d-107">Ta funkcja korzysta z funkcji uczenia maszynowego, która ułatwia firmom prognozowanie przepływów pieniężnych bardziej dokładnie niż wcześniej.</span><span class="sxs-lookup"><span data-stu-id="5948d-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="5948d-108">Może również pomagać menedżerom w podejmowaniu decyzji optymalizujących szanse sprzedaży w kontekście ich bieżącego stanu środków pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="5948d-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="5948d-109">W przypadku większości firm zarządzanie przepływem gotówki i uruchamianie prognozowania przepływów pieniężnych jest żmudnym, powtarzającym się i ręcznym procesem.</span><span class="sxs-lookup"><span data-stu-id="5948d-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="5948d-110">Większość firm opiera się na rozwiązaniach Microsoft Excel o różnych stopniach złożoności.</span><span class="sxs-lookup"><span data-stu-id="5948d-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="5948d-111">Dokładne prognozowania przepływu pieniężnego może sprawiać trudności z następujących przyczyn:</span><span class="sxs-lookup"><span data-stu-id="5948d-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="5948d-112">Dane nie są dostępne dla osób podejmujących decyzje, ponieważ są rozrzucone w wielu miejscach, w tym:</span><span class="sxs-lookup"><span data-stu-id="5948d-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="5948d-113">System księgowo-finansowy lub system planowania zasobów przedsiębiorstwa</span><span class="sxs-lookup"><span data-stu-id="5948d-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="5948d-114">Oprogramowanie do planowania finansowego</span><span class="sxs-lookup"><span data-stu-id="5948d-114">Financial planning software</span></span>
  - <span data-ttu-id="5948d-115">Plik programu Excel</span><span class="sxs-lookup"><span data-stu-id="5948d-115">Excel</span></span>
  - <span data-ttu-id="5948d-116">Dodatkowe aplikacje</span><span class="sxs-lookup"><span data-stu-id="5948d-116">Additional software applications</span></span> 
- <span data-ttu-id="5948d-117">Prognozowanie opiera się na wewnętrznej bazie wiedzy, która znajduje się w „silosach” należących do poszczególnych domen lub działów.</span><span class="sxs-lookup"><span data-stu-id="5948d-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="5948d-118">Mierzenie dokładności prognozowania przepływów pieniężnych po zrealizowaniu transakcji finansowych jest niepewne i trudne.</span><span class="sxs-lookup"><span data-stu-id="5948d-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="5948d-119">Szczegóły możliwości prognoz przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="5948d-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="5948d-120">Funkcja prognoz przepływów pieniężnych obejmuje następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="5948d-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="5948d-121">Ułatwia integrację danych przepływów pieniężnych z systemów zewnętrznych z systemem Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="5948d-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="5948d-122">Prognozy przepływów pieniężnych mogą również wykorzystywać strukturę importu i eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="5948d-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="5948d-123">Ta struktura ułatwia integrację z usługą OData dla programu Excel.</span><span class="sxs-lookup"><span data-stu-id="5948d-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="5948d-124">Można również połączyć dane z wielu źródeł w celu utworzenia wszechstronnego rozwiązania do przepływu pieniężnego.</span><span class="sxs-lookup"><span data-stu-id="5948d-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="5948d-125">Wprowadza inteligentny stan środków pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="5948d-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="5948d-126">Stan środków pieniężnych jest tworzony na podstawie zachowań płatności odbiorcy w celu przewidywania, kiedy firma może oczekiwać wpłaty gotówkowej na swoje konta.</span><span class="sxs-lookup"><span data-stu-id="5948d-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="5948d-127">Ponadto analizuje historyczne wzorce płatności dla dostawców, aby przewidzieć, kiedy zostaną prawdopodobnie zapłacone przyszłe faktury i zamówienia.</span><span class="sxs-lookup"><span data-stu-id="5948d-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="5948d-128">Wprowadza inteligentne prognozowanie przepływów pieniężnych dla długoterminowej prognozy, używając prognozowania szeregu czasowego poprzez automatyczną integrację z AI Builder.</span><span class="sxs-lookup"><span data-stu-id="5948d-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="5948d-129">Umożliwia zapisywanie konkretnego stanu środków pieniężnych lub ich prognoz, ich edytowanie, a następnie łatwe porównywanie prognozy z rzeczywistymi finansami i mierzenie jej skuteczności.</span><span class="sxs-lookup"><span data-stu-id="5948d-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="5948d-130">Umożliwia analizę warunkową poprzez porównanie migawek.</span><span class="sxs-lookup"><span data-stu-id="5948d-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="5948d-131">Można na przykład utworzyć wiele migawek reprezentujących optymistyczne, pesymistyczne i najbardziej realistyczne scenariusze przepływów pieniężnych, a następnie porównać i wyświetlić te różnice.</span><span class="sxs-lookup"><span data-stu-id="5948d-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="5948d-132">Umożliwia wyświetlanie prognozy przepływów pieniężnych w wielu walutach, między firmami oraz filtrowanie i wyświetlanie przepływów pieniężnych związanych z kontem bankowym.</span><span class="sxs-lookup"><span data-stu-id="5948d-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="5948d-133">Umożliwia filtrowanie i wyświetlanie kont bankowych, które są powiązane z wymiarami finansowymi.</span><span class="sxs-lookup"><span data-stu-id="5948d-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="5948d-134">Funkcja prognozowania przepływów pieniężnych w systemie Dynamics 365 Finance pozwala organizacji na przekształcanie żmudnych, złożonych i powtarzających się projekcji przepływów pieniężnych w prosty, zautomatyzowany proces.</span><span class="sxs-lookup"><span data-stu-id="5948d-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="5948d-135">Automatyzacja najbardziej żmudnych aspektów prognozowania przepływów pieniężnych umożliwia skoncentrowanie się na krytycznych decyzjach przekładających się na pożądane wyniki biznesowe.</span><span class="sxs-lookup"><span data-stu-id="5948d-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="5948d-136">Konfigurowanie wymiarów dla prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="5948d-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="5948d-137">Nowa karta na stronie **Konfiguracja prognozowania przepływów pieniężnych** umożliwia kontrolowanie wymiarów finansowych, które mają być używane do filtrowania, w obszarze roboczym **Prognozowanie przepływów pieniężnych**.</span><span class="sxs-lookup"><span data-stu-id="5948d-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="5948d-138">Ta karta będzie wyświetlana tylko wtedy, gdy jest włączona funkcja prognoz przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="5948d-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="5948d-139">Na karcie **Wymiary** wybierz z listy wymiary, które mają być użyte do filtrowania, a następnie za pomocą klawiszy strzałek przenieś je do prawej kolumny.</span><span class="sxs-lookup"><span data-stu-id="5948d-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="5948d-140">Do filtrowania danych prognozy przepływów pieniężnych można wybrać tylko dwa wymiary.</span><span class="sxs-lookup"><span data-stu-id="5948d-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
