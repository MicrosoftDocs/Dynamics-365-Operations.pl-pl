---
title: Kody kroku grupy czynności
description: Ten temat zawiera przegląd kodów etapów grupy czynności oraz sposobu ich używania.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c28134b9be92802196b4861cbd20801419ef8d23
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212682"
---
# <a name="wave-step-codes"></a>Kody kroku grupy czynności

[!include [banner](../includes/banner.md)]

Kody etapów grupy czynności są kodami, które użytkownicy mogą konfigurować i stosować w celu łączenia określonych wystąpień metod grupy czynności z odpowiednim szablonem. Szablony te obejmują szablony uzupełniania, konteneryzacji, drukowania etykiet, kompilowania i sortowania.

Jeśli nie są używane kody etapów grupy czynności, użytkownicy muszą wprowadzać dowolny tekst, aby odwoływać się do określonego szablonu z instancji metody Wave. Tekst niezależny jest podatny na błędy, ponieważ użytkownicy muszą upewnić się, że tekst etapu grupy czynności dodawany dla konkretnej metody w szablonie grupy czynności jest dokładnie zgodny z tekstem kroku grupy czynności w szablonie docelowym.

Kody etapów grupy czynności dla konkretnego typu kroku są konfigurowane na osobnej stronie. Dla każdej instancji metody etapów grupy czynności, która wymaga kodu kroku grupy czynności, należy wybrać kod etapu grupy rozwijanej. Wybór na liście rozwijanej zastępuje wprowadzanie tekstu swobodnego i pomaga zmniejszyć ryzyko i wpływ błędu człowieka. Kody ustawień służą do łączenia metody kroku grupy czynności w szablonie grupy czynności z docelowym szablonem metody.

> [!NOTE]
> Użycie funkcji kodów kroków grupy czynności jest opcjonalne. Jest ona włączona dla całej organizacji dla wszystkich firm.

## <a name="setup-demo"></a>Pokaz instalacji 

W tym pokazie trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana wersja demonstracyjna **USMF** danych firmy.

### <a name="enable-wave-step-codes"></a>Włącz kody kroku grupy czynności

Aby włączyć funkcję kodów etapów grupy czynności, należy wykonać poniższe kroki

1. Przejdź do obszaru **Zarządzanie funkcjami**.
2. Wybierz opcję włączenia funkcji o nazwie **Kod kroku grupy czynności w całej organizacji**.

Wszystkie istniejące teksty niezależne kroków grupy czynności we wszystkich firmach są uaktualniane do nowej struktury. Po ukończeniu tego uaktualniania dla wszystkich firm funkcja jest włączona. Jeśli nie można włączyć tej funkcji dla co najmniej jednej firmy, funkcja nie jest włączona dla żadnych firm.

Podczas włączania weryfikacje są wykonywane w trakcie uaktualniania danych. Jeśli uaktualnienie nie powiedzie się, zostanie wyświetlony komunikat o błędzie. Uaktualnienie może zakończyć się niepowodzeniem z powodu następujących konfliktów:

- Istnieją zduplikowane teksty etapów grupy czynności
- Dostosowania jest możliwe.
- Tekst niezależny krok fazy wyjścia skojarzony z wystąpieniem metody kroku grupy czynności nie pasuje do oczekiwanego typu szablonu.

Po rozwiązaniu wszelkich konfliktów, które zostaną zidentyfikowane podczas weryfikacji, można ponownie spróbować włączyć funkcję.

Po włączeniu funkcji będzie dostępna strona **Kody etapów grupy czynności** (**Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody etapów grupy czynności**). Ta strona zawiera listę kodów etapów grupy czynności, które zostały uaktualnione po włączeniu funkcji kodów kroków grupy czynności w całej organizacji.

### <a name="create-new-wave-step-codes"></a>Tworzenie nowych kodów etapów grupy czynności

Do tworzenia i usuwania **kodów etapów grupy czynności** służą strony kody etapów grupy czynności

Każdy nowy kod kroku grupy czynności i skojarzony z nim identyfikator musi być unikatowy we wszystkich typach etapów grupy czynności i musi być zdefiniowany dla konkretnego typu kroku grupy czynności

### <a name="apply-wave-step-codes"></a>Zastosuj kody etapów grupy czynności — informacje

Po zdefiniowaniu odpowiednich kodów etapów można je stosować do metod procesu typu grupy czynności.

Aby zastosować kody etapów grupy czynności, należy przejść do odpowiedniego szablonu docelowego. Oto szablony docelowe, dla których mają być wskazywane kody etapów grupy czynności:

- **Szablony uzupełniania zapasów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów.
- **Ładowanie szablonów kompilacji:** Zarządzanie magazynem \> Ustawienia \> Ładowanie \> Ładowanie szablonów kompilacji
- **Sortowanie szablonów:** zarządzania magazynem \> Ustawienia \> Pakowanie \> Szablony sortowania wychodzącego opakowań
- **Szablony kontenerów:** Wybierz kolejno opcje Zarządzanie magazynem \> Ustawienia \> Kontenery \> Szablony kompilacji kontenerów
- **Szablony drukowania etykiet:** zarządzanie magazynem \> ustawienia \> Wybór trasy dokumentów \> szablony etykiet grupy czynności

Szablony z tej listy są stosowane, gdy odwołują się się do metody procesu grupy czynności wybranej w szablonie grupy czynności Jeśli kod kroku grupy czynności dla metody procesu Wave w szablonie grupy czynności jest zgodny z kodem kroku grupy czynności w jednym z typów szablonów, jest stosowany szablon.

### <a name="sample-scenario"></a>Przykładowy scenariusz

Poniższa procedura pomaga zagwarantować, że utworzony szablon uzupełnienia zapasów będzie stosowany do szablonu grupy czynności

1. Przejdź do **zarządzanie magazynem \> ustawienia \> grupy czynności \> kody grup czynności** i utwórz kod kroku grupy czynności dla typu **uzupełnienia**.
2. Wybierz **Zarządzanie magazynem \> Ustawienia \> Uzupełnienie \> Szablony uzupełniania zapasów** i stwórz szablon.
3. W szablonie uzupełnienia wybierz kod kroku grupy czynności, który został utworzony dla typu **uzupełnienia**.
4. Przejdź do **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grup czynności** a następnie wybierz szablon grupy czynności, który ma być używany.
5. W szablonie **metody** na skróconej karcie wybierz metodę **uzupełniania zapasów**.
6. W **Kod czynności grupowych** wybierz kod kroku grupy czynności, który został utworzony dla typu szblonu uzupełnienia.

Wykonaj następujące kroki dla każdej firmy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]