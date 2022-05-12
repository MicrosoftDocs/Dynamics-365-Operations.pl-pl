---
title: Wybierz pomiędzy Store Commerce a Cloud POS
description: Ten temat wyjaśnia kluczowe różnice między Store Commerce i Cloud POS oraz opisuje różne czynniki, które detaliści wdrażający Dynamics 365 Commerce powinni rozważyć, aby pomóc sobie w dokonaniu najlepszego wyboru dla swoich wymagań.
author: jblucher
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b62e1737bc9e3b9d9e25a7a88e693a9aece80776
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629297"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>Wybierz pomiędzy Store Commerce a Cloud POS

[!include [banner](includes/banner.md)]

Ten temat wyjaśnia kluczowe różnice między Store Commerce i Cloud POS oraz opisuje różne czynniki, które detaliści wdrażający Dynamics 365 Commerce powinni rozważyć, aby pomóc sobie w dokonaniu najlepszego wyboru dla swoich wymagań. Daje także osobom odpowiedzialnych za wdrożenie dodatkowe tło, wskazówki i wytyczne dotyczące czynników, które powinni wziąć pod uwagę podczas wdrażania Dynamics 365 Commerce. Zapoznanie się z tymi wytycznymi oraz przestrzeganie ich w procesie wdrożenia pozwoli uniknąć osobom odpowiedzialnym za wdrożenie problemów, które mogą wpłynąć na zadowolenie klienta lub wydajność.

## <a name="insights"></a>Wgląd

Środowisko Commerce zapewnia szeroką gamę opcji topologii oraz wdrożeń. W związku z tym sprzedawcy detaliczni mogą wybierać składniki i konfiguracje najlepiej dostosowane do ich wymagań biznesowych i technologicznych. Jednym z aspektów wdrożenia, jaki należy uważnie przeanalizować, jest wybór platformy oraz wyglądu formularza dla składnika punktu sprzedaży (POS).

### <a name="pos-platform-and-form-factor-considerations"></a>Uwagi dotyczące platformy i wyglądu formularza punktu sprzedaży

Środowisko Commerce obsługuje następujące opcje punktu sprzedaży:

- Aplikacja Store Commerce w Microsoft Windows
- Aplikacja Store Commerce w Android i iOS
- Cloud POS (CPOS) obsługujący przeglądarki Microsoft Edge i Google Chrome
- Modern POS (MPOS) dla Microsoft Windows (MPOS zostanie wycofane z użytku w październiku 2023 roku). 

We wszystkich przypadkach punkt sprzedaży (Store Commerce i CPOS) opiera się na tym samym podstawowym kodzie aplikacji. Jest to istotne z następujących powodów:

- Interfejs użytkownika (UI) jest jednakowy, niezależnie od platformy czy wyglądu formularza.
- Większość możliwości funkcjonalnych jest taka sama, niezależnie od platformy czy wyglądu formularza. Istnieją jednak pewne ważne różnice. Różnice te zostały wskazane w tym temacie.
- W każdym sklepie warianty POS mogą być łączone i działać równolegle. Na przykład do obsługi głównych rejestrów sprzedawca detaliczny może używać Store Commerce zainstalowanego na komputerach z systemem Windows. Jednak sprzedawca może uzupełniać te rejestry za pomocą terminali działających w oparciu o przeglądarkę lub urządzeń przenośnych.
- Można w prosty sposób korzystać z dostosowań i rozszerzeń między platformami i wyglądami formularzy. Główny kod aplikacji jest współdzielony, dlatego większość dostosowań można wdrażać jednorazowo zamiast wielokrotnie.

### <a name="store-commerce-vs-cpos"></a>Store Commerce a CPOS

Choć punkty Store Commerce i CPOS są w dużej mierze podobne, istnieją jednak między nimi pewne istotne różnice, z którymi należy się zapoznać.

#### <a name="store-commerce"></a>Store Commerce

Store Commerce to aplikacja na urządzenia stacjonarne, która jest instalowana i obsługiwana na urządzeniu.

- **Windows** – Aplikacja Store Commerce dla Windows zawiera cały kod aplikacji, Commerce Runtime (CRT) i Hardware Station (HWS).
- **iOS/Android** — w przypadku tych platform aplikacja pełni funkcję hosta dla kodu aplikacji CPOS. Innymi słowy, kod aplikacji pochodzi z serwera CPOS, który jest umieszczony na Commerce Scale Unit. Aby uzyskać więcej informacji, zobacz [Omówienie Commerce Scale Unit](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>Punkt sprzedaży w chmurze (CPOS)

Punkt CPOS jest uruchamiany w przeglądarce, dlatego aplikacja nie jest zainstalowana na urządzeniu. Zamiast tego to przeglądarka przechodzi do kodu aplikacji z serwera CPOS> Dlatego punkt CPOS nie ma bezpośredniego dostępu do sprzętu punktu sprzedaży ani nie może pracować w trybie offline.

### <a name="store-deployment-considerations"></a>Zagadnienia dotyczące wdrażania w sklepie

Oprócz platformy i wyglądu formularza, sprzedawcy detaliczni muszą również wybrać opcję wdrożenia w sklepie. W poniższej tabeli przedstawiono konfiguracje dostępne dla poszczególnych opcji punktu sprzedaży.

| Aplikacja punktu sprzedaży            | Commerce Scale Unit | Dostępne w trybie offline | Lokalna pomoc techniczna HWS |
|----------------------------|---------------------|-------------------|-------------------|
| Aplikacja Store Commerce w Windows | Chmura lub RSSU       | Tak               | Tak               |
| Aplikacja Store Commerce w Android | Chmura lub RSSU       | Nie                | Tak               |
| Aplikacja Store Commerce w iOS     | Chmura lub RSSU       | Nie                | Nie                |
| Cloud POS                  | Chmura lub RSSU       | Nie                | Nie                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

Commerce Scale Unit jest składnikiem obsługującym składnik CRT. CRT zawiera całą logikę biznesową wykorzystywaną przez punkt sprzedaży i zapewnia dostęp do bazy danych kanałów. Podczas pracy w trybie online wszystkie klienty punktu sprzedaży w sklepie korzystają z serwera Commerce Scale Unit. Commerce Scale Unit można wdrożyć w chmurze lub w sklepie.

#### <a name="offline-mode"></a>Tryb offline

Store Commerce dla Windows obsługuje tryb offline. W trybie offline można kontynuować przetwarzania sprzedaży, nawet wtedy, gdy punkt sprzedaży jest odłączony od Commerce Scale Unit. Po przywróceniu łączności można go zsynchronizować z bazą danych kanałów. Store Commerce wykorzystuje własne wbudowane wystąpienie CRT i tymczasowo używa własnego lokalnego źródła danych (bazy danych offline serwera SQL). Aby uzyskać więcej informacji na temat funkcji pracy w trybie offline, zobacz [Funkcjonalność offline punktu sprzedaży](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>Zagadnienia dotyczące urządzeń peryferyjnych / sprzętu punktu sprzedaży

Sprzedawcy detaliczni muszą również wziąć pod uwagę dostęp punktu sprzedaży do sprzętu i urządzeń peryferyjnych, takich jak drukarki, szuflady na gotówkę i terminale płatnicze. Stacje sprzętowe mogą być przypisane do rejestru punktu sprzedaży lub współdzielone przez rejestry w sklepie.

| Aplikacja punktu sprzedaży            | Lokalny HWS OPOS | Sieciowe urządzenia peryferyjne | Wspólne wsparcie HWS |
|----------------------------|----------------|---------------------|--------------------|
| Aplikacja Store Commerce w Windows | Tak            | Tak                 | Tak                |
| Aplikacja Store Commerce w Android | Nie             | Tak                 | Tak                |
| Aplikacja Store Commerce w iOS     | Nie             | Nie                  | Tak                |
| Cloud POS                  | Nie             | Nie                  | Tak                |

Aby uzyskać więcej informacji na temat stacji sprzętowych, zobacz [Konfigurowanie i instalowanie stacji sprzętowej handlu detalicznego](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>Uwagi dotyczące implementacji

Podczas planowania wdrożenia punktu sprzedaży w sklepach należy wziąć pod uwagę następujące informacje:

- **Wymagań funkcjonalne** — podstawowe procesy biznesowe i możliwości są takie same, niezależnie od platformy, wyglądu formularza czy topologii wdrożenia. W związku z tym większość sprzedawców detalicznych nie musi brać pod uwagę wymagań funkcjonalnych, planując wdrożenie.
- **Łączność** — dostępność sieci (sieć rozległa \[sieć WAN\] i sieć lokalna \[LAN\]) stanowi podstawową kwestię, która wymaga zachowania pewnej ostrożności. Wszelkie korzyści finansowe i uproszczenia uzyskane dzięki zastosowaniu niestacjonarnego rozwiązania z hostingiem w chmurze stają się nieistotne, jeśli system jest niedostępny dla procesów krytycznych dla prowadzenia biznesu.

    O ile łączność w przypadku danego urządzenia jest bardzo niezawodna i elastyczna lub o ile sprzedawca detaliczny nie dopuszcza pewnego czasu przestoju, zaleca się zastosowanie jednej z następujących opcji:

    - Korzystanie z punktu Store Commerce dla systemu Windows z aktywnym trybem pracy offline.
    - Wdróż lokalnie Commerce Scale Unit.

    Te dwie opcje nie wykluczają się wzajemnie. W przypadku większości niezawodnych topologii sprzedawcy detaliczni mogą wdrożyć lokalną jednostkę RSSU w celu ograniczenia zależności od łączności internetowej lub dostępności usługi Azure, a ponadto mogą również wdrożyć rejestry punktu sprzedaży na urządzeniu z włączonym trybem offline na wypadek wystąpienia problemu z serwerem lokalnym lub siecią.

- **Urządzenia sprzętowe/peryferyjne** — jednym z istotnych aspektów systemu punktu sprzedaży Retail jest jego zdolność do obsługi urządzeń peryferyjnych punktu sprzedaży, takich jak drukarki, szuflady na gotówkę i terminale płatnicze. Co prawda wszystkie dostępne opcje punktu sprzedaży mogą korzystać z urządzeń peryferyjnych, jednak wyłącznie punkt Store Commerce dla systemu Windows obsługuje je w sposób bezpośredni. W przypadku wszystkich innych zastosowań wymagana jest co najmniej jedna stacja sprzętowa. Takie podejście zwiększa elastyczność, jednak wymaga wdrożenia, skonfigurowania i obsługi dodatkowych składników.
- **Wymagania systemowe** — wymagania systemowe dla aplikacji punktu sprzedaży się różnią. Przed podjęciem ostatecznej decyzji należy sprawdzić najnowsze informacje. Przykładowo punkt CPOS obsługuje więcej systemów operacyjnych, ponieważ działa w przeglądarce. Aby uzyskać więcej informacji na temat wymagań systemowych, zobacz [Wymagania systemowe dla wdrożeń w chmurze](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **Wdrażanie i obsługa** — złożoność wymagań związanych z wdrożeniem i obsługą może być różna w zależności od wybranych opcji wdrożenia i aplikacji. Na przykład w przypadku wdrożenia punktu CPOS hostowanego w chmurze nie ma potrzeby instalowania i aktualizowania go na każdym urządzeniu. Dlatego to podejście w znacznym stopniu zmniejsza złożoność oraz koszt. Jednak w przypadku wdrożenia punktu Store Commerce na każdym rejestrze i aktywacji trybu offline w połączeniu z wdrożeniem współdzielonych stacji sprzętowych znacznie zwiększa się liczba punktów końcowych wymagających zarządzania.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
