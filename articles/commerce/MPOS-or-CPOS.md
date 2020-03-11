---
title: Wybór między aplikacjami Modern POS (MPOS) i Cloud POS
description: W tym temacie objaśniono kluczowe różnice między Modern POS a Cloud POS. Opisano w nim również różne czynniki, jakie sprzedawcy detaliczni wdrażający Dynamics 365 Commerce powinni brać pod uwagę przy doborze rozwiązania najlepiej odpowiadającego ich wymaganiom.
author: jblucher
manager: AnnBe
ms.date: 10/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 508fda28d8f815f030e7b163709393f70904a5fd
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057701"
---
# <a name="choose-between-modern-pos-mpos-and-cloud-pos"></a>Wybór między aplikacjami Modern POS (MPOS) i Cloud POS

[!include [banner](includes/banner.md)]

W temacie tym przedstawiono również dodatkowe tło, wskazówki oraz wytyczne dla osób odpowiedzialnych za wdrożenie w zakresie czynników, jakie powinni wziąć pod uwagę podczas wdrażania oprogramowania Dynamics 365 Commerce. Zapoznanie się z tymi wytycznymi oraz przestrzeganie ich w procesie wdrożenia pozwoli uniknąć osobom odpowiedzialnym za wdrożenie problemów, które mogą wpłynąć na zadowolenie klienta lub wydajność.

## <a name="insights"></a>Wgląd

Środowisko Commerce zapewnia szeroką gamę opcji topologii oraz wdrożeń. W związku z tym sprzedawcy detaliczni mogą wybierać składniki i konfiguracje najlepiej dostosowane do ich wymagań biznesowych i technologicznych. Jednym z aspektów wdrożenia, jaki należy uważnie przeanalizować, jest wybór platformy oraz wyglądu formularza dla składnika punktu sprzedaży (POS).

### <a name="pos-platform-and-form-factor-considerations"></a>Uwagi dotyczące platformy i wyglądu formularza punktu sprzedaży

Środowisko Commerce obsługuje następujące opcje punktu sprzedaży:

- Modern POS (MPOS) dla systemu Microsoft Windows
- MPOS dla Microsoft Windows Phone
- Nowoczesny punkt sprzedaży dla urządzenia Apple iPad lub tabletu z systemem Google Android
- Cloud POS (CPOS) obsługujący przeglądarki Microsoft Edge, Internet Explorer Google Chrome

We wszystkich przypadkach punkt sprzedaży (nowoczesny i w chmurze) opiera się na tym samym podstawowym kodzie aplikacji. Jest to istotne z następujących powodów:

- Interfejs użytkownika (UI) jest jednakowy, niezależnie od platformy czy wyglądu formularza.
- Większość możliwości funkcjonalnych jest taka sama, niezależnie od platformy czy wyglądu formularza. Istnieją jednak pewne ważne różnice. Różnice te zostały wskazane w tym temacie.
- Różne warianty punktów sprzedaży można łączyć i uruchamiać jednocześnie w tym samym sklepie. Na przykład do obsługi głównych rejestrów sprzedawca detaliczny może używać nowoczesnego punktu sprzedaży zainstalowanego na komputerach z systemem Windows. Jednak sprzedawca może uzupełniać te rejestry za pomocą terminali działających w oparciu o przeglądarkę lub urządzeń przenośnych.
- Można w prosty sposób korzystać z dostosowań i rozszerzeń między platformami i wyglądami formularzy. Główny kod aplikacji jest współdzielony, dlatego większość dostosowań można wdrażać jednorazowo zamiast wielokrotnie.

### <a name="mpos-vs-cpos"></a>Nowoczesny punkt sprzedaży a punkt sprzedaży w chmurze

Choć punkty MPOS i CPOS są w dużej mierze podobne, istnieją jednak między nimi pewne istotne różnice, z którymi należy się zapoznać.

#### <a name="mpos"></a>MPOS

Punkt MPOS przeznaczony do urządzeń z systemem Windows, iOS lub Android jest aplikacją spakowaną, zainstalowaną i obsługiwaną na danym urządzeniu.

- **Windows** — aplikacja MPOS dla systemu Windows zawiera cały kod instalacji oraz osadzone środowisko uruchomieniowe Commerce runtime (CRT). 
- **iOS/Android** — w przypadku tych platform aplikacja pełni funkcję hosta dla kodu aplikacji CPOS. Innymi słowy, kod aplikacji pochodzi z serwera CPOS w Microsoft Azure lub Commerce Scale Unit. Aby uzyskać więcej informacji, zobacz [Omówienie Commerce Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>Punkt sprzedaży w chmurze (CPOS)

Punkt CPOS jest uruchamiany w przeglądarce, dlatego aplikacja nie jest zainstalowana na urządzeniu. Zamiast tego to przeglądarka przechodzi do kodu aplikacji z serwera CPOS> Dlatego punkt CPOS nie ma bezpośredniego dostępu do sprzętu punktu sprzedaży ani nie może pracować w trybie offline.

### <a name="store-deployment-considerations"></a>Zagadnienia dotyczące wdrażania w sklepie

Oprócz platformy i wyglądu formularza, sprzedawcy detaliczni muszą również wybrać opcję wdrożenia w sklepie. W poniższej tabeli przedstawiono konfiguracje dostępne dla poszczególnych opcji punktu sprzedaży.

| Aplikacja punktu sprzedaży         | Commerce Scale Unit | Dostępne w trybie offline |
|-------------------------|---------------|-------------------|
| MPOS dla systemu Windows        | Chmura lub RSSU | Tak               |
| MPOS dla systemu iOS lub Android | Chmura lub RSSU | Nie                |
| Cloud POS               | Chmura lub RSSU | Nie                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

Commerce Scale Unit jest składnikiem obsługującym składnik CRT. CRT zawiera całą logikę biznesową wykorzystywaną przez punkt sprzedaży i zapewnia dostęp do bazy danych kanałów. Podczas pracy w trybie online wszystkie klienty punktu sprzedaży w sklepie korzystają z serwera Commerce Scale Unit. Commerce Scale Unit można wdrożyć w chmurze lub w sklepie.

#### <a name="offline-mode"></a>Tryb offline

MPOS dla systemu Windows obsługuje tryb offline. W trybie offline można kontynuować przetwarzania sprzedaży, nawet wtedy, gdy punkt sprzedaży jest odłączony od Commerce Scale Unit. Po przywróceniu łączności można go zsynchronizować z bazą danych kanałów. Punkt MPOS wykorzystuje własne wbudowane wystąpienie CRT i tymczasowo używa własnego lokalnego źródła danych (bazy danych offline serwera SQL). Aby uzyskać więcej informacji na temat funkcji pracy w trybie offline, zobacz [Funkcjonalność offline punktu sprzedaży](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Zagadnienia dotyczące urządzeń peryferyjnych / sprzętu punktu sprzedaży

Sprzedawcy detaliczni muszą również wziąć pod uwagę dostęp punktu sprzedaży do sprzętu i urządzeń peryferyjnych, takich jak drukarki, szuflady na gotówkę i terminale płatnicze. Bezpośrednią komunikację z tymi urządzeniami obsługuje wyłącznie punkt MPOS dla systemu Windows. Dostęp do tych urządzeń z punktu MPOS dla systemów Windows Phone, iOS lub Android oraz punktu sprzedaży w chmurze wymaga zastosowania stacji sprzętowej. Stacje sprzętowe mogą być przypisane do rejestru punktu sprzedaży lub współdzielone przez rejestry w sklepie. Aby uzyskać więcej informacji na temat stacji sprzętowych, zobacz [Konfigurowanie i instalowanie stacji sprzętowej handlu detalicznego](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Uwagi dotyczące implementacji

Podczas planowania wdrożenia punktu sprzedaży w sklepach należy wziąć pod uwagę następujące informacje:

- **Wymagań funkcjonalne** — podstawowe procesy biznesowe i możliwości są takie same, niezależnie od platformy, wyglądu formularza czy topologii wdrożenia. W związku z tym większość sprzedawców detalicznych nie musi brać pod uwagę wymagań funkcjonalnych, planując wdrożenie.
- **Łączność** — dostępność sieci (sieć rozległa \[sieć WAN\] i sieć lokalna \[LAN\]) stanowi podstawową kwestię, która wymaga zachowania pewnej ostrożności. Wszelkie korzyści finansowe i uproszczenia uzyskane dzięki zastosowaniu niestacjonarnego rozwiązania z hostingiem w chmurze stają się nieistotne, jeśli system jest niedostępny dla procesów krytycznych dla prowadzenia biznesu.

    O ile łączność w przypadku danego urządzenia jest bardzo niezawodna i elastyczna lub o ile sprzedawca detaliczny nie dopuszcza pewnego czasu przestoju, zaleca się zastosowanie jednej z następujących opcji:

    - Korzystanie z punktu MPOS dla systemu Windows z aktywnym trybem pracy offline.
    - Wdróż lokalnie Commerce Scale Unit.

    Te dwie opcje nie wykluczają się wzajemnie. W przypadku większości niezawodnych topologii sprzedawcy detaliczni mogą wdrożyć lokalną jednostkę RSSU w celu ograniczenia zależności od łączności internetowej lub dostępności usługi Azure, a ponadto mogą również wdrożyć rejestry punktu sprzedaży na urządzeniu z włączonym trybem offline na wypadek wystąpienia problemu z serwerem lokalnym lub siecią.

- **Urządzenia sprzętowe/peryferyjne** — jednym z istotnych aspektów systemu punktu sprzedaży Retail jest jego zdolność do obsługi urządzeń peryferyjnych punktu sprzedaży, takich jak drukarki, szuflady na gotówkę i terminale płatnicze. Co prawda wszystkie dostępne opcje punktu sprzedaży mogą korzystać z urządzeń peryferyjnych, jednak wyłącznie punkt MPOS dla systemu Windows obsługuje je w sposób bezpośredni. W przypadku wszystkich innych zastosowań wymagana jest co najmniej jedna stacja sprzętowa. Takie podejście zwiększa elastyczność, jednak wymaga wdrożenia, skonfigurowania i obsługi dodatkowych składników.
- **Wymagania systemowe** — wymagania systemowe dla aplikacji punktu sprzedaży się różnią. Przed podjęciem ostatecznej decyzji należy sprawdzić najnowsze informacje. Przykładowo punkt CPOS obsługuje więcej systemów operacyjnych, ponieważ działa w przeglądarce. Aby uzyskać więcej informacji na temat wymagań systemowych, zobacz [Wymagania systemowe dla wdrożeń w chmurze](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Wdrażanie i obsługa** — złożoność wymagań związanych z wdrożeniem i obsługą może być różna w zależności od wybranych opcji wdrożenia i aplikacji. Na przykład w przypadku wdrożenia punktu CPOS hostowanego w chmurze nie ma potrzeby instalowania i aktualizowania go na każdym urządzeniu. Dlatego to podejście w znacznym stopniu zmniejsza złożoność oraz koszt. Jednak w przypadku wdrożenia punktu MPOS na każdym rejestrze i aktywacji trybu offline w połączeniu z wdrożeniem współdzielonych stacji sprzętowych znacznie zwiększa się liczba punktów końcowych wymagających zarządzania.
