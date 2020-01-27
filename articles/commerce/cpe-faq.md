---
title: Często zadawane pytania dotyczące środowiska wersji zapoznawczej usługi Commerce
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska aplikacji Microsoft Dynamics 365 Commerce w wersji zapoznawczej.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 53e593931850d6b8b22bb756d5828f742416aa4d
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906100"
---
# <a name="commerce-preview-environment-faq"></a>Często zadawane pytania dotyczące środowiska wersji zapoznawczej usługi Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące środowiska aplikacji Microsoft Dynamics 365 Commerce w wersji zapoznawczej.

**Czy mogę przenieść moje zaproszenie do środowiska wersji zapoznawczej usługi Commerce do innej dzierżawy?**

Tak. W przypadku transferów zaproszeń można użyć [formularza transferu wersji zapoznawczej usługi Commerce](https://aka.ms/Dynamics365CommercePreviewTransferForm).

**Jak długo trwa transfer zaproszenia?**

Transfer trwa średnio około od trzech do pięciu dni roboczych. Mogą jednak obowiązywać wyjątki.

**Czy środowisko wersji zapoznawczej usługi Commerce współdziała z projektami aplikacji Dynamics 365 Finance lub Dynamics 365 Supply Chain?**

Nr Środowisko wersji zapoznawczej usługi Commerce działa tylko z projektami aplikacji Dynamics 365 Retail.

**Czy możemy użyć środowiska wersji zapoznawczej usługi Commerce jako sklepu internetowego dla klientów, którzy obecnie wdrażają aplikację Retail?**

Nr Środowisko wersji zapoznawczej usługi Commerce to tylko środowisko oceny. Jeśli wymagane jest środowisko dla klienta, który implementuje aplikację Retail, skontaktuj się z firmą Microsoft.

**Czy środowisko wersji zapoznawczej usługi Commerce może służyć do aprowizowania funkcji e-Commerce jako uzupełnienie istniejącej aplikacji/środowiska, które implementuje aplikację Retail?**

Nr Środowisko wersji zapoznawczej usługi Commerce jest obecnie dostępne tylko w nowych środowiskach, które zostały wdrożone w projektach jednostek magazynowych (SKU) aplikacji Retail z danymi pokazów z wersji 10.0.6.

**Jakie koszty są zaangażowane we wdrażanie środowiska wersji zapoznawczej usługi Commerce na platformie Microsoft Azure za pośrednictwem usług Microsoft Dynamics Lifecycle Services (LCS)?**

Retail jest jedynym składnikiem hostowanym w ramach subskrypcji. Inne składniki, takie jednostka Retail Cloud Scale Unit (RCSU) i e-Commerce, będą obsługiwane w subskrypcjach Microsoft. Możesz użyć [kalkulatora cen platformy Azure](https://azure.microsoft.com/pricing/calculator/), aby oszacować ten koszt.

**Które regiony geograficzne platformy Azure są obecnie obsługiwane w środowisku wersji zapoznawczej usługi Commerce?**

Środowisko wersji zapoznawczej usługi Commerce można wdrożyć tylko w regionie Ameryka Północna.

**Czy istnieje wirtualny dysk twardy (VHD) z możliwością pobrania, który ma pełną opcję maszyny wirtualnej OneBox?**

Jednostka Dynamics 365 Retail Cloud Scale Unit (RCSU) i usługa e-Commerce to w całości oprogramowanie jako usługa (SaaS) i muszą być hostowane w chmurze.

**Jak długo można używać środowiska wersji zapoznawczej usługi Commerce?**

Środowisko wersji zapoznawczej usługi Commerce ma 30-dniowy limit czasu od daty aprowizacji e-Commerce.

**Czy mogę przedłużyć limit czasu dla mojego środowiska wersji zapoznawczej usługi Commerce?**

Tak. Możesz skontaktować się z zespołem pomocy technicznej przy użyciu [formularza rozszerzenia wersji zapoznawczej usługi Commerce](https://aka.ms/Dynamics365CommercePreviewExtensionForm).

**Czy możemy wysłać wiele żądań dotyczących środowiska wersji zapoznawczej usługi Commerce?**

Przyznajemy limit przydziału obejmujący jedno środowisko wersji zapoznawczej usługi Commerce dla każdego zaakceptowanego żądania. Jeśli potrzebujesz więcej niż jednego środowiska wersji zapoznawczej, skontaktuj się z firmą Microsoft. Informacje kontaktowe można znaleźć w następnej sekcji.

## <a name="dynamics-365-commerce-preview-environment-contact-information"></a>Informacje kontaktowe dotyczące środowiska wersji zapoznawczej Dynamics 365 Commerce

Aby skontaktować się z firmą Microsoft, jeśli masz pytania lub wnioski dotyczące środowiska wersji zapoznawczej usługi Commerce, odwiedź [grupę wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce w serwisie Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) w celu uzyskania pomocy.

Jeśli podczas próby uzyskania dostępu do grupy w serwisie Yammer wystąpią problemy, możesz skontaktować się z firmą Microsoft pocztą elektroniczną pod adresem <Dynamics365Commerce@microsoft.com>. Ten adres e-mail nie jest aktywnie monitorowany. W związku z tym należy oczekiwać opóźnienia odpowiedzi.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska wersji zapoznawczej usługi Commerce](cpe-overview.md)

[Aprowizowanie środowiska wersji zapoznawczej usługi Commerce](provisioning-guide.md)

[Konfigurowanie środowiska wersji zapoznawczej usługi Commerce](cpe-post-provisioning.md)

[Konfigurowanie funkcji opcjonalnych środowiska wersji zapoznawczej usługi Commerce](cpe-optional-features.md)
