---
title: Parametry modułu Zarządzanie rabatami
description: W tym temacie opisano stronę Parametry zarządzania rabatami. Ta strona zawiera ustawienia mające wpływ na księgowanie, aktualizacje stanu, sekwencje numerów i inne zachowanie.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8f5c9734b2480329eed246bcbbfe3bd6e9991e0b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688999"
---
# <a name="rebate-management-parameters"></a>Parametry modułu Zarządzanie rabatami

[!include [banner](../includes/banner.md)]

Strona **Parametry zarządzania rabatami** służy do definiowania ustawień stosowanych w module **Zarządzanie rabatami**. Te ustawienia mające wpływ na księgowanie, aktualizacje stanu, sekwencje numerów i inne zachowania. Ustawienia na tej stronie są udostępniane w różnych firmach i mogą być modyfikowane przez użytkowników z odpowiednimi uprawnieniami zabezpieczeń.

Aby otworzyć stronę **Parametry zarządzania rabatami**, przejdź do **Zarządzanie rabatem \> Ustawienia \> Rebate management parameters**. Następnie ustaw pola, które są opisane w kolejnych podrozdziałach.

## <a name="rebate-management-tab"></a>Karta Zarządzanie rabatami

W poniższej tabeli opisano pola dostępne na karcie **Zarządzanie rabatami** na stronie **parametry zarządzania rabatami**.

| Pole | opis |
|---|---|
| Stan domyślny | Umożliwia wybór domyślnego stanu wszystkich nowych transakcji. Aby zdefiniować zestaw wartości stanu dostępnych do wyboru, należy użyć strony [**Stany rabatów**](rebate-statuses.md). |
| Przetwarzanie według wymiaru | Umożliwia wybór, czy transakcje dotyczące udostępniania, rabatów i odpisów mają być przetwarzane według wymiaru finansowego. Gdy opcja jest włączona, system używa wymiarów finansowych z transakcji źródłowych w transakcjach docelowych. |
| Sprawdź, czy wcześniej zaksięgowano | <p>Umożliwia wybranie zachowania systemu w przypadku, gdy niezaksięgowane transakcje rabatowe są przetwarzane więcej niż raz dla tego samego okresu:</p><ul><li>**Ostrzeżenie** — system umożliwia użytkownikom zastępowanie wierszy oryginalnych transakcji, ale wyświetlane jest ostrzeżenie.</li><li>**Błąd** — System uniemożliwia użytkownikom zastępowanie wierszy oryginalnych transakcji i wyświetlany jest komunikat o błędzie. |
| Automatyczne księguj arkusze | Pozwala określić, czy system ma automatycznie księguje proponowane arkusze. Te arkusze obejmują arkusze dzienne, które są używane do rezerw i potrąceń od odbiorcy, a także arkusze faktur podatkowych od dostawców. |
| Automatycznie publikuj faktury niezależne | Pozwala określić, czy system ma automatycznie księguje faktury niezależne. Ta opcja dotyczy wyłącznie faktur tekstowych, dla których typem płatności są *potrącenia odbiorcy faktury podatkowej*. |
| Odwołanie do zamówienia pozycji rabatowej | Zaznacz odwołanie do rabatu, które ma być rabatem na zamówieniach sprzedaży i zakupu generowanych w ramach procesu rabatowego (*Brak*, *Umowa zarządzania rabatem* i potrącenia, *Numer zarządzania rabatem*, *Numer transakcji rabatu* lub *Notatki o dokumentach*). |
| Używanie procesu odbioru | <p>Ustaw tę opcję na wartość *Tak*, aby użyć porcesu odbioru. W ten sposób można oznaczyć transakcje, które w ramach zarządzania rabatami tworzy jako „odebrane” lub „nieodebrane”, a następnie księgować tylko te transakcje, których dotyczy roszczenie.</p><p>Na przykład rabaty są obliczane dla miesięcznych transakcji, ale odbiorca pozostał na to dwa dni. W takim przypadku transakcje niepobrane zostaną utworzone ponownie przy następnym uruchomieniu funkcji *procesu* dla następnego okresu.</p><p>Jeśli zostanie ustawiona opcja *Nie*, wszystkie transakcje roszczenia zostaną zaksięgowane.</p> |
| Uwzględnij arkusz typów zamówień | W przypadku umów lub wierszy umów, w których typem transakcji jest *Zamówienie*, ta opcja określa, czy ma być uwzględniane zamówienie sprzedaży typu *Arkusz*. Jeśli te typy zamówień są używane w scenariuszach, w których rabat nie ma jeszcze zastosowania, zapewnia elastyczność. |

## <a name="number-sequences-tab"></a>Karta Sekwencje numerów

Karta **Sekwencje numerów** na stronie **Parametry zarządzania rabatami** służy do przypisywania kodów sekwencji numerów do różnych sekwencji numerów, które są używane przez zarządzanie rabatami. W poniższej tabeli opisano cel każdej z tych sekwencji numerów. Aby uzyskać więcej informacji o sekwencjach numerów, zobacz [Przegląd sekwencji numerów](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) i jego tematy pokrewne.

| Odwołanie | opis |
|---|---|
| Zarządzanie rabatami — umowa | Sekwencja numerów przypisuje unikatową wartość klucza do każdej umowy rabatowej. Ten klucz jest używany podczas tworzenia umów. |
| Zarządzanie rabatami — liczba | Sekwencja numerów przypisuje unikatową wartość klucza do każdego rabatu. Klucz ten służy do identyfikacji relacji rabatów. |
| Numer transakcji rabatu | Sekwencja numerów przypisuje unikatową wartość klucza do każdej transakcji rabatowej. Klucz ten służy do identyfikacji ransakcji rabatów. |
| Faktura podatkowa | Sekwencja numerów przypisuje unikatową wartość klucza do każdej faktury rabatowej. Ten klucz jest używany podczas automatycznego księgowana arkuszy rabatowych. |

## <a name="feature-visibility-tab"></a>Karta Widoczność funkcji

Zarządzanie rabatami powoduje dodanie funkcji (pól i funkcji) do kilku często używanych stron w Microsoft Dynamics 365 Supply Chain Management. Strony te zawierają strony związane z zamówieniami sprzedaży i transakcjami sprzedaży. Jeśli używasz funkcji Zarządzania rabatami, te funkcje muszą być widoczne wszędzie, aby było można z nich korzystać. Jeśli nie używasz Zarządzania rabatami, możesz ukryć funkcje, aby nie przeszkadzały.

Na karcie **Widoczność funkcji** na stronie **Parametry zarządania rabatami** ustaw opcję **Aktywuj** na wartość *Tak*, aby funkcje zarządania rabatami były widoczne, gdy tylko są dostępne. Ustaw wartość *Nie*, aby ukryć funkcje na wspólnych stronach poza modułem **zarządania rabatami**. Jednak nawet jeśli jest ustawiona opcja *Nie*, sam moduł, w tym strona **Parametry zarządania rabatami**, pozostanie dostępny dla użytkowników, którzy mają odpowiednie uprawnienia dostępu do tego modułu.
