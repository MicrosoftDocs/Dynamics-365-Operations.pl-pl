---
title: Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych
description: W tym temacie znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych. Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1cde9321259753bd0cacab3706c7f8455598ff3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232496"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="a0781-104">Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych</span><span class="sxs-lookup"><span data-stu-id="a0781-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0781-105">W tym temacie znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="a0781-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="a0781-106">Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.</span><span class="sxs-lookup"><span data-stu-id="a0781-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="a0781-107">Dlaczego przepływ pieniężny jest pokazywany tylko dla jednej firmy?</span><span class="sxs-lookup"><span data-stu-id="a0781-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="a0781-108">Prognozowanie przepływów pieniężnych jest konfigurowane i obliczane dla firmy.</span><span class="sxs-lookup"><span data-stu-id="a0781-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="a0781-109">Raporty usługi Power BI i możliwości prognozowania przepływów pieniężnych w narzędziu Finance Insights pokazują wyniki.</span><span class="sxs-lookup"><span data-stu-id="a0781-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="a0781-110">Prognozowanie przepływów pieniężnych musi być ustawione dla każdej firmy, dla której ma być ustawiona prognoza.</span><span class="sxs-lookup"><span data-stu-id="a0781-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="a0781-111">Przejrzyj konfigurację prognozowania przepływów pieniężnych we wszystkich firmach.</span><span class="sxs-lookup"><span data-stu-id="a0781-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="a0781-112">Alternatywnie przejrzyj konfigurację wszystkich firm do prognozowania przepływów pieniężnych i upewnij się, że są ustawione zgodnie z zamierzeniami.</span><span class="sxs-lookup"><span data-stu-id="a0781-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="a0781-113">Dlaczego usługa Power BI nie wyświetla wszystkich danych dotyczących przepływów pieniężnych?</span><span class="sxs-lookup"><span data-stu-id="a0781-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="a0781-114">Aby prognozy przepływów pieniężnych mogły pojawić się w widokach usługi Power BI, należy wykonać kilka kroków.</span><span class="sxs-lookup"><span data-stu-id="a0781-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="a0781-115">Przejrzyj następującą listę kontrolną i upewnij się, że każdy krok został ukończony:</span><span class="sxs-lookup"><span data-stu-id="a0781-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="a0781-116">Skonfiguruj przepływy pieniężne dla każdej firmy.</span><span class="sxs-lookup"><span data-stu-id="a0781-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="a0781-117">W parametrach księgi głównej należy ustawić walutę systemową i systemowy typ kursu wymiany.</span><span class="sxs-lookup"><span data-stu-id="a0781-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="a0781-118">Ustaw walutę rozliczeniową księgi i typ kursu wymiany.</span><span class="sxs-lookup"><span data-stu-id="a0781-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="a0781-119">Wprowadź kursy wymiany między walutą transakcji a walutą rozliczeniową.</span><span class="sxs-lookup"><span data-stu-id="a0781-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="a0781-120">Wprowadź kursy wymiany między walutą rozliczeniową a walutą systemu.</span><span class="sxs-lookup"><span data-stu-id="a0781-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="a0781-121">Wprowadź kursy wymiany między walutą rozliczeniową a walutą każdego banku.</span><span class="sxs-lookup"><span data-stu-id="a0781-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="a0781-122">Dlaczego usługa Power BI przepływu środków pieniężnych działała w poprzednich wersjach, ale jest teraz pusta?</span><span class="sxs-lookup"><span data-stu-id="a0781-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="a0781-123">Upewnij się, że skonfigurowano miary „Miara przepływu pieniężnego V2” i „LedgerCovLiquidityMeasurement” z magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="a0781-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="a0781-124">Aby uzyskać więcej informacji dotyczących pracy z danymi w magazynie jednostek, zobacz [integrację Power BI z magazynem jednostek](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Sprawdź, czy zostały wykonane wszystkie kroki wymagane do wyświetlenia zawartości Power BI.</span><span class="sxs-lookup"><span data-stu-id="a0781-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="a0781-125">Aby uzyskać więcej informacji, zobacz [Omówienie operacji gotówkowych - zawartość Power BI](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="a0781-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="a0781-126">Czy jednostki magazynu jednostek zostały odświeżone?</span><span class="sxs-lookup"><span data-stu-id="a0781-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="a0781-127">Należy okresowo odświeżać jednostki, aby mieć pewność, że dane są aktualne i dokładne.</span><span class="sxs-lookup"><span data-stu-id="a0781-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="a0781-128">Aby ręcznie odświeżyć określoną jednostkę, przejdź do **Administrowanie systemem \> Konfiguracja \> Magazyn jednostek**, wybierz tę jednostkę, a następnie wybierz opcję **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="a0781-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="a0781-129">Dane mogą być również aktualizowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a0781-129">The data can also be updated automatically.</span></span> <span data-ttu-id="a0781-130">Na stronie **Magazyn jednostek** ustaw opcję **Automatyczne odświeżanie** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a0781-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]