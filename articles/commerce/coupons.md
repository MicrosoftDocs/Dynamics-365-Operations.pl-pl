---
title: Kupony
description: Ten artykuł stanowi omówienie możliwości związanych z kuponami w Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 20427a04a552ddec013daa6576ec64ab7046e95f
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709767"
---
# <a name="coupons"></a>Kupony

[!include [banner](../includes/banner.md)]

Ten artykuł stanowi omówienie możliwości związanych z kuponami w Microsoft Dynamics 365 Commerce.

Kupony to kody i kody kreskowe używane w celu dodawania rabatów do transakcji. Sprzedawcy detaliczni rozprowadzają kupony potencjalnym lub istniejącym klientom, aby pomóc w zwiększeniu rozpoznania marki, konwersji napędzania, zachowaniu bazy klientów, napędzeniu sprzedaży i ostatecznie zwiększeniu przychodów. Kupony stały się jednym z najpopularniejszych narzędzi marketingowych i są nową normą sprzedaży w handlu elektronicznym.

W Dynamics 365 Commerce kupony są połączone z rabatami i są uznawane za dodatkowe sprawdzanie poprawności oprócz rabatów. Każdy kupon jest związany z jednym rabatem, a połączony rabat definiuje zestaw produktów, dla których kupon jest ważny.

Grupy cenowe skojarzone z rabatem określają warunki, do których może zostać użyty kupon. Te warunki obejmują grupy klientów i kanały sprzedaży. Kupony zawierają także **Limit wykorzystania** i **Wymagane przez klienta** właściwości, których można użyć do skonfigurowania opcjonalnych ograniczeń wykorzystania.

Każdy kupon może mieć wiele kodów kuponów i kodów paskowych kuponów, a każdy kod może mieć własny zakres dat wejścia w życie i stan. Jeśli kod ma stan **Nieaktywny**, nie można go używać w żadnym kanale.

## <a name="set-up-a-coupon"></a>Konfigurowanie kuponu

Zanim będzie można utworzyć kupon, należy skonfigurować kod kreskowy kuponu i dwie numeracje kuponu.

Aby skonfigurować kupon w centrali Commerce headquarters, wykonaj kroki opisane poniżej.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Zarządzanie zapasami \> Kody kreskowe i etykiety \> Znaki maski**.
1. Wybierz opcję **Dodaj**, aby utworzyć znak maski typu **Kod kuponu**. W polu **Znak** możesz wybrać dowolny nieużywany znak.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Zarządzanie zapasami \> Kody kreskowe i etykiety \> Konfiguracja maski kodu kreskowego**.
1. Wybierz opcję **Nowe**, aby utworzyć maskę kodu typu **Kod kuponu**.
1. Wybierz kolejno opcje **Handel detaliczny i inny \> Zarządzanie zapasami \> Kody kreskowe i etykiety \> Konfiguracja kodu kreskowego**.
1. Wybierz **Nowe**, by utworzyć nowy kod kreskowy, który wykorzystuje utworzoną maskę kodów kreskowych.
1. Wybierz kolejno opcje **Administrowanie organizacją \> Sekwencje numerów**.
1. Tworzenie dwóch sekwencji numerów:

    1. Jedna sekwencja dla odwołania **Numer kuponu**. Ta sekwencja definiuje identyfikator unikatowy kuponu.
    1. Jedna sekwencja dla odwołania **Identyfikator kodu kuponu**. Ta sekwencja określa unikatowy identyfikator każdego kodu kuponu na kuponie.

    Dla obu numeracji należy w polu **Zakres** ustawić wartość **Firma**. W większości przypadków obie sekwencje numerów powinny być automatycznie wygenerowane.

1. Przejdź do opcji **Parametry rozwiązania Commerce \> Ceny i rabaty \> Kupony**.
1. Ustaw pole **Maska kodów paska kuponu** na utworzony wcześniej kod kreskowy.
1. Przejdź do **Parametry rozwiązania Commerce \> Sekwencje numerów**.
1. Wybierz sekwencje numerów utworzone wcześniej dla odwołań **Numer kuponu** i **Identyfikator kodu kuponu**.

Aby skonfigurować kupon, należy utworzyć rabat i kupon osobno, a następnie połączyć je, wybierając rabat w polu **Rabat** konfiguracji kuponu. Gdy kupon jest połączony z rabatem, pola **Stan**, **Data wejścia w życie** i **Data ważności** połączonego rabatu stają się tylko do odczytu, ponieważ wartości są ustalane na podstawie stanu kuponu i okresu ważności. Gdy stan kuponu jest ustawiony na **Aktywny**, stan połączonego rabatu jest automatycznie aktualizowany na **Włączony**. Podobnie, gdy stan kuponu jest ustawiony na **Nieaktywny**, stan połączonego rabatu jest automatycznie aktualizowany na **Wyłączony**.

## <a name="use-a-coupon"></a>Używanie kuponu

Aby dodać kupon do transakcji sprzedaży w punkt sprzedaży (POS) rozwiązania Commerce, można użyć kodu kuponu lub kodu paska kuponu. Aby użyć kodu kuponu, wybierz operację **Dodaj kod kuponu**, a następnie wprowadź kod. Aby użyć kodu paska kuponu, albo zeskanuj kod paska, używając urządzenie do skanowania, albo wprowadź go za pomocą klawiatury numerycznej na ekranie **Transakcja**.

Sprzedawcy detaliczni czasami chcą, aby kasjerzy mogli udzielać klientom rabatów o stałej kwocie z powodu wad produktów lub z powodu wad produktu, ale nie chcą drukować kodów kuponów i dystrybuować ich do kasjerów. W tym przypadku można ustawić dla kuponu opcję **Zastosuj bez kodu kuponu** na wartość **Tak**. Kasjerzy punktu sprzedaży mogą następnie używać funkcji **Zastosuj kupon** wewnątrz operacji **Wyświetlanie dostępnych rabatów**, aby dodać kupon do transakcji bez ręcznego wprowadzania kodu. Jeśli istnieje wiele kodów kuponów dla kuponu, system automatycznie wybiera pierwszy aktywny kod i stosuje go w transakcji.

Aby dodać kupon do zamówienia sprzedaży dla centrum obsługi, użytkownik biura obsługi musi wybrać **Kupony** na karcie **Zarządzaj** w okienku akcji na stronie zamówienia sprzedaży.

Aby dodać kupon do zamówienia w sklepie handlu elektronicznego, kupujący może wprowadzić kod kuponu w polu **kodu promocyjnego** w koszyku.

Po dodaniu kuponu do zamówienia sprzedaży aparat cen natychmiast uruchamia ponowne obliczenie dla całego zamówienia, niezależnie od tego, czy jest włączone obliczanie opóźnione.

> [!NOTE]
> W wersji Commerce 10.0.30 i wcześniejszej, gdy użytkownicy biura obsługi dodadzą kupon do zamówienia sprzedaży biura obsługi, muszą wybrać opcję **Oblicz ponownie** w grupie **Oblicz** na karcie **Sprzedaż** w okienku akcji, aby zastosować rabat skojarzony z tym kuponem.

## <a name="coupon-usage-limit"></a>Ograniczenia użycia kuponu

Kupony można skonfigurować do ograniczonego użycia. Limit użycia można zdefiniować dla klienta, kanału lub jako limit globalny. Limit użycia jest wymuszany dla kodu kuponu na kuponie. Na przykład kupon jednorazowego użytku, który zawiera dwa kody kuponu, może zostać wykorzystany dwukrotnie, po jednym razie dla każdego kodu kuponu.

Kupony mogą być używane w różnych kanałach sprzedaży. Jednak w przypadku biura obsługi kupony ograniczonego użycia mogą być stosowane tylko wtedy, gdy jest włączone ustawienie **Włącz zakończenie zamówienia** dla kanału biura obsługi. Jeśli ustawienie **Włącz zakończenie zamówienia** jest wyłączone, można stosować tylko kupony bez ograniczeń.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
