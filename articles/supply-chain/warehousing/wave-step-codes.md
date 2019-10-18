---
title: Kody kroku grupy czynności
description: Ten temat zawiera przegląd kodów etapów grupy czynności oraz sposobu ich używania.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992364"
---
# <a name="wave-step-codes"></a>Kody kroku grupy czynności

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a>Kody etapów grupy czynności — informacje

Kody etapów grupy czynności są kodami, które użytkownicy mogą konfigurować i stosować w celu łączenia określonych wystąpień metod grupy czynności z odpowiednim szablonem. Szablony te obejmują szablony uzupełniania, konteneryzacji, drukowania etykiet, kompilowania i sortowania.

Jeśli nie są używane kody etapów grupy czynności, użytkownicy muszą wprowadzać dowolny tekst, aby odwoływać się do określonego szablonu z instancji metody Wave. Tekst niezależny jest podatny na błędy, ponieważ użytkownicy muszą upewnić się, że tekst etapu grupy czynności dodawany dla konkretnej metody w szablonie grupy czynności jest dokładnie zgodny z tekstem kroku grupy czynności w szablonie docelowym.

Kody etapów grupy czynności dla konkretnego typu kroku są konfigurowane na osobnej stronie. Dla każdej instancji metody etapów grupy czynności, która wymaga kodu kroku grupy czynności, należy wybrać kod etapu grupy rozwijanej. Wybór na liście rozwijanej zastępuje wprowadzanie tekstu swobodnego i pomaga zmniejszyć ryzyko i wpływ błędu człowieka. Kody ustawień służą do łączenia metody kroku grupy czynności w szablonie grupy czynności z docelowym szablonem metody.

> [!NOTE]
> Użycie funkcji kodów etapów grupy czynności jest opcjonalne, a dla każdej firmy. Dlatego jeśli określona firma używa tej funkcji, wszystkie istniejące kody kroków grupy w tej firmie zostaną uaktualnione do nowej struktury.

## <a name="setup-demo"></a>Pokaz instalacji 

W tym pokazie trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana wersja demonstracyjna **USMF** danych firmy.

### <a name="enable-wave-step-codes"></a>Włącz kody kroku grupy czynności

Aby włączyć funkcję kodów etapów grupy czynności, należy wykonać poniższe kroki

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
2. Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie dostawcy** dla opcji **Przetwarzanie grupy czynności** wybierz ustawienie **Tak**.

Wszystkie istniejące teksty niezależne krokami wyjścia są uaktualniane do nowej struktury. Po ukończeniu tego uaktualnienia dla firmy nie jest już dostępna opcja **Włącz kody etapów grupy czynności** na stronie **parametrów zarządzania magazynem**.

Sprawdzanie poprawności zostało przeprowadzone podczas uaktualniania systemu, a Jeśli uaktualnienie nie powiedzie się, zostanie wyświetlony komunikat o błędzie. Uaktualnienie może zakończyć się niepowodzeniem z powodu następujących konfliktów:

- Istnieją zduplikowane teksty etapów grupy czynności
- Dostosowania jest możliwe.
- Tekst niezależny krok fazy wyjścia skojarzony z wystąpieniem metody kroku grupy czynności nie pasuje do oczekiwanego typu szablonu.

Po rozwiązaniu wszelkich konfliktów, które zostaną zidentyfikowane podczas sprawdzania poprawności, można ponownie uruchomić proces uaktualniania.

Po pomyślnym uaktualnieniu systemu będzie dostępna strona **Kody etapów grupy czynności** (**Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Kody etapów grupy czynności**). Ta strona zawiera listę kodów etapów grupy czynności, które zostały uaktualnione po włączeniu funkcji kodów etapów grupy czynności

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
