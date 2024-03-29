---
title: Przegląd typu planu
description: W programie Microsoft Dynamics 365 Human Resources typ planu to nadrzędna grupa konkretnych typów świadczeń.
author: twheeloc
ms.date: 08/24/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ca14156c165ca3f536fc0120ebd03883284eb18
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336968"
---
# <a name="plan-type-overview"></a>Przegląd typu planu

[!include [banner](../includes/preview-banner.md)]

Typ planu to nadrzędna grupa konkretnych typów świadczeń. Każdy typ planu ma kod typu planu, który określa reguły typu planu. Na przykład typ planu **Podstawowe ubezpieczenie na życie** może mieć kod typu planu **Ubezpieczenie na życie**, ponieważ jest to rodzaj planu ubezpieczenia na życie i musi być zgodny z regułami określonymi w typie planu o kodzie **Ubezpieczenie na życie**. Innym typem planu może być **Dodatkowe ubezpieczenie na życie**. Ten typ planu będzie również kod typu planu **Ubezpieczenie na życie**.

Każdy typ planu wskazuje, czy pracownik może się zarejestrować w jednym, czy w wielu planach tego typu. Na przykład pracownik prawdopodobnie może się zarejestrować w obu planach o typie Ubezpieczenie na życie — **Podstawowe ubezpieczenie na życie** i **Dodatkowe ubezpieczenie na życie**. Pracownik prawdopodobnie może się zarejestrować tylko w jednym planie o typie Medyczny.

Jeśli typ planu uwzględnia kontakty, to wskazuje, czy te kontakty są beneficjentami, czy osobami na osobami na utrzymaniu. Na przykład typ planu **Podstawowe ubezpieczenie na życie** będzie miał beneficjentów, natomiast typ planu Podstawowe ubezpieczenie medyczne będzie miał osoby na utrzymaniu. W niektórych przypadkach plan może nie mieć żadnych kontaktów osobistych. Na przykład: Konto wydatków elastycznych lub Dodatek parkingowy.


Typ planu może określać opcje objęcia świadczeniami. Opcje objęcia świadczeniami definiuje się na stronie **Opcje objęcia świadczeniem**. Opcja objęcia świadczeniem może określać kwotę świadczenia lub kontakty kwalifikujące się do danego typu planu. Jeśli na przykład typ kontaktu to **Beneficjent**, opcja objęcia świadczeniem powinna określać warunki, jakie beneficjent ma prawo otrzymać podczas realizacji świadczenia. Jeśli typem kontaktu jest **Osoba na utrzymaniu**, opcja objęcia świadczeniem powinna definiować relację między osobą na utrzymaniu a pracownikiem etatowym. 

> [!IMPORTANT]
> Strona **Typy planów** zawiera kluczowe dane, które wpływają na opcje dostępne podczas tworzenia nowego planu świadczeń:
>
> - **Kod typu planu** — to pole ma wpływ na to, co jest wyświetlane na karcie **Konfiguracja** podczas konfigurowania rzeczywistej korzyści.  
> - **Jednoczesna rejestracja** — to pole określa, czy dozwolone jest wiele rejestracji. (W przypadku planu medycznego pole to jest zazwyczaj **Jedna rejestracja**.)
> - **Typ kontaktu** — to pole umożliwia dodawanie osób pozostających na utrzymaniu lub beneficjentów do planu. Jeśli jest ustawiona na **Brak**, pracownicy, którzy zarejestrują się w świadczeniach, nie będą mieli możliwości wybrania beneficjenta lub osoby pozostającej na utrzymaniu.
> - **Opcje zapotrzebowania** — to pole służy do łączenia opcji zapotrzebowania z typami planu. Definiuje albo osoby, które będą objęte tym typem planu, albo kwoty ubezpieczenia dostępne dla tego typu planu. Na przykład można określić, że ubezpieczenie dla typu planu medycznego będzie dostępne tylko dla pracownika, pracownika i jednej innej osoby lub pracownika i jego rodziny.

## <a name="create-plan-types"></a>Tworzenie typów planu

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Typy planów**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Typ planu** | Unikatowa nazwa identyfikująca typ planu. |
   | **Opis** | Opis typu planu. |
   | **Kod typu planu** | Z rozwijanej listy wartości wybierz kod typu planu. Na liście kodów typów planów są wyświetlane wszystkie typy planów obsługiwane w bieżącej wersji programu. |
   | **Rejestrowanie współbieżne** | Określa, czy pracownik etatowy może się rejestrować w wielu planach świadczeń o tym samym typie planu, czy tylko w jednym planie świadczeń o danym typie planu. |
   | **Typ kontaktu** | Określa rolę kontaktu osobistego. Możliwe wartości: puste pole, Osoba na utrzymaniu i Beneficjent. Pole **Typu kontaktu** można pozostawić puste, jeśli typ planu nie wymaga podania osoby na utrzymaniu ani beneficjenta dla danej opcji objęcia świadczeniem. |

4. Aby skonfigurować opcje zmian sytuacji życiowej, wybierz opcję **Akcje**, a następnie opcję **Opcje zmian sytuacji życiowej**. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Typ planu** | Typ planu, dla którego mają zostać skonfigurowane opcje zmiany sytuacji życiowej. |
   | **Identyfikator typu zdarzenia zmiany sytuacji życiowej** | Identyfikator typu zmiany sytuacji życiowej. |
   | **Zmień opcję objęcia świadczeniem** | Określa, czy pracownik etatowy może zmienić opcje objęcia świadczeniami w trakcie zmiany sytuacji życiowej. |
   | **Zmień na nowy plan** | Określa, czy pracownik etatowy może zmienić plany w trakcie zmiany sytuacji życiowej. |
   | **Automatycznie ponownie otwórz sprawdzanie uprawnień** | Określa, w trakcie zdarzenia zmiany sytuacji życiowej sprawdzanie uprawnień do rejestracji świadczeń ma być automatycznie ponownie otwarte. |
   | **Okres rejestracji zdarzenia zmiany sytuacji życiowej** | Określa w dniach okno raportowania dotyczące zdarzenia zmiany sytuacji życiowej. **Uwaga**: Jeśli nie wprowadzisz ilości, system przyjmie, że okno raportowania ma wartość zero, i nie przetworzy zmiany sytuacji życiowej. |
   | **Edytowalne tylko przez administratorów** | Określa, czy administratorzy mogą anulować lub edytować plan podczas wydarzenia z życia. W obszarze roboczym **Samoobsługa pracownicza** pracownik nie może wprowadzać żadnych zmian. |
   | **Automatycznie anuluj plan** | Określa, czy plan powinien być automatycznie anulowany podczas wydarzenia z życia. Po przetworzeniu zmian zdarzenia życia opcja **Automatycznie anuluj plan** zachowuje wybór planu. Zostaną usunięte tylko stany **Potwierdzone** lub **Wyewidencjonowane**. Plan pozostaje wybrany. W związku z tym pracownicy, którzy nie dokonają wyboru planu w okresie rejestracji zdarzenia życia, nie przegrają wyboru planu. 

5. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
