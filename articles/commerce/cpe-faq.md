---
title: Często zadawane pytania dotyczące środowiska oceny rozwiązania Dynamics 365 Commerce
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska oceny Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e8a3e760353b351d42aff82c0d372d2aca350cd2
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343565"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Często zadawane pytania dotyczące środowiska oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska oceny Microsoft Dynamics 365 Commerce.

## <a name="can-we-use-the-commerce-evaluation-environment-as-an-e-commerce-storefront-for-customers-that-currently-implement-retail"></a>Czy możemy użyć środowiska oceny usługi Commerce jako sklepu internetowego dla klientów, którzy obecnie wdrażają aplikację Retail?

Nr Środowisko oceny Commerce jest przeznaczone wyłącznie do oceny. Jeśli wymagane jest środowisko dla klienta, który implementuje aplikację Retail, skontaktuj się z firmą Microsoft.

## <a name="can-the-commerce-evaluation-environment-be-used-to-provision-the-e-commerce-features-on-top-of-an-existing-applicationenvironment-that-implements-retail"></a>Czy środowisko oceny usługi Commerce może służyć do aprowizowania funkcji handlu elektronicznego jako uzupełnienie istniejącej aplikacji/środowiska, które implementuje aplikację Retail?

Nie (głównie). Składniki oceny aplikacji Commerce są dostępne tylko w środowiskach zgodnych z konfiguracjami określonymi w wymaganiach wstępnych i przewodniku obsługi administracyjnej. Ponadto wymagane podstawowe dane demonstracyjne nie będą dostępne w środowiskach wdrożonych z początkową wersją wcześniejszą niż 10.0.8. 

## <a name="what-costs-are-involved-in-deploying-the-commerce-evaluation-environment-on-microsoft-azure-via-microsoft-dynamics-lifecycle-services-lcs"></a>Jakie koszty są zaangażowane we wdrażanie środowiska oceny usługi Commerce na platformie Microsoft Azure za pośrednictwem usług Microsoft Dynamics Lifecycle Services (LCS)?

Tradycyjne środowisko demonstracyjne//główne Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce (maszyna wirtualna \[VM\]) będzie hostowana w Twojej subskrypcji platformy Azure. Możesz użyć [kalkulatora cen platformy Azure](https://azure.microsoft.com/pricing/calculator/), aby oszacować ten koszt.

Inne składniki, takie jak Commerce Scale Unit, Commerce Site Builder i Twoja witryna handlu elektronicznego, będą dostępne jako oprogramowanie jako usługa (SaaS) i będą obsługiwane przez firmę Microsoft.

## <a name="which-azure-geographies-are-currently-supported-for-the-commerce-evaluation-environment"></a>Które regiony geograficzne platformy Azure są obecnie obsługiwane w środowisku oceny usługi Commerce?

Środowisko oceny usługi Commerce można wdrożyć tylko w regionie Ameryka Północna.

## <a name="is-there-a-downloadable-virtual-hard-disk-vhd-that-has-the-complete-onebox-virtual-machine-vm-option"></a>Czy istnieje wirtualny dysk twardy (VHD) z możliwością pobrania, który ma pełną opcję maszyny wirtualnej OneBox?

Dynamics 365 Commerce i Commerce Scale Unit to w całości oprogramowanie jako usługa (SaaS) i muszą być hostowane w chmurze.

## <a name="how-long-can-the-commerce-evaluation-environment-be-used"></a>Jak długo można używać środowiska oceny usługi Commerce?

Środowisko oceny Commerce ma 30-dniowy limit czasu od daty udostępnienia składników SaaS, takich jak Commerce Scale Unit, narzędzie do tworzenia witryn Commerce i Twoja witryna handlu elektronicznego.

## <a name="can-i-extend-the-time-limit-for-my-commerce-evaluation-environment"></a>Czy mogę przedłużyć limit czasu dla mojego środowiska oceny usługi Commerce?

Wydłużenie limitu czasu jest wyjątkiem od normy i jest brane pod uwagę oddzielnie dla każdego przypadku. Aby uzyskać pomoc, skontaktuj się z partnerem firmy Microsoft.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
