---
title: Kalendarze i planowanie główne
description: Ten temat zawiera omówienie kalendarzy łańcucha dostaw i ich wpływu na planowanie główne.
author: t-benebo
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a53efb753a75916c85dc4a45a3c64872a7f5d32
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908378"
---
# <a name="calendars-and-master-planning"></a>Kalendarze i planowanie główne

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie kalendarzy łańcucha dostaw i ich wpływu na planowanie główne.  Opisano różne kalendarze używane w aparacie planowania głównego łącznie z ich wpływem na daty wysyłki i odbioru zamówień planowanych. Podano też zalecenia odnośnie do przypisywania, używania i aktualizacji kalendarzy.

## <a name="definition-of-a-calendar"></a>Definicja kalendarze

Można zdefiniować kalendarz używany w organizacji na stronie w **Administracja organizacją > Ustawienia > Kalendarze > Kalendarze**. 

Każdy wpis daty w kalendarzu może być mieć wartość **otwarta** lub **zamknięta** lub **kalendarz podstawowy**. Określa się to w kolumnie **Formant** na stronie **Czasy pracy**. Dla każdej daty: 
- **Otwarta** -wskazuje, że praca jest wykonywana w wybranym dniu. Kalendarz będzie aktualizowany zgodnie z szablonem czasu pracy.
- **Zamknięta** -wskazuje, że praca nie jest wykonywana tym dniu. 
- **Kalendarz podstawowy** - wskazuje, że określona dat odziedziczy czasy pracy i opcje otwarty/zamknięty z kalendarza podstawowego. Dlatego kiedy kalendarz podstawowy jest aktualizowany, wybrany kalendarz nie odziedziczy z niego czasów operacji. 

Dla każdej daty zamkniętej zostanie automatycznie przypisane pole wyboru **Zamknięte dla pobrania**. Dla dat otwartych można ręcznie wybrać opcję **Zamknięte dla pobrania**. Oznacza to, że praca jest wykonywana w danym dniu, ale wysyłka nie jest wykonywana. 

## <a name="calendars-that-affect-master-planning"></a>Kalendarze, które mają wpływ na planowanie główne

### <a name="calendar-for-a-coverage-group"></a>Kalendarz dla grupy zapotrzebowania
Grupa zapotrzebowania wskazuje wspólny zestaw parametrów używanych do uzupełnienia zapasów, które należą do danej grupy zapotrzebowania. 

Aby dodać kalendarz do grupy zapotrzebowania, przejdź do **Planowanie główne > Ustawienia > Zapotrzebowanie > Grupy zapotrzebowania**. Znajdź grupę zapotrzebowania, do której chcesz przypisać kalendarz, a następnie wybierz ją w polu **Kalendarz**.

Grupa zapotrzebowania można być przypisana do różnych stron: 
    - Na stronie **Szczegóły zwolnionego produktu** towaru. Aby wyświetlić grupy zapotrzebowania dla towaru, przejdź do **Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty** i wybierz towar, aby przejść na stronę **Szczegóły zwolnionego produktu**. Widoczna jest grupa grupy zapotrzebowania na towar na karcie skrócone **Plan**.
    - Na stronie **Zapotrzebowanie na towar**. Na stronie szczegółów zwolnionego produktu kliknij przycisk **Zapotrzebowanie na towar**, aby przejść do strony zapotrzebowania towaru. Na karcie Przegląd widać różne parametry określające sposób uzupełniania zapasów w zależności od wielkości oddziału, magazynu i produktów. Grupa zapotrzebowania dla każdego towaru będzie dziedziczona z grupy zapotrzebowania na stronie **Szczegóły zwolnionego produktu**. Można to zastąpić przy użyciu opcji **Zapotrzebowanie na towary** lub **Zastąp ustawienia grupy** na karcie **Ogólne**.
    - Na stronie **Parametry planowania głównego**. Jeśli towar nie ma ustawionej grupy zapotrzebowania na poprzedniej stronie, planowanie główne podejmie ustawienia ogólnej grupy zapotrzebowania w parametrach planowania głównego. Ustawia się to w polu **Planowanie główne > Ustawienia > Parametry planowania głównego** w polu **Ogólna grupa zapotrzebowania**. 

### <a name="calendar-for-a-vendor"></a>Kalendarz dla dostawcy
Aby określić dni robocze dla dostawcy, można przypisać kalendarz zakupów do dostawcy na stronie **Ustawienia domyślne zamówienia zakupu** dla dostawcy. 

Aby ustawić kalendarz dla dostawcy, należy utworzyć kalendarz w **Administrowanie organizacją > Kalendarze > Kalendarze**. Jeśli kalendarz został już utworzony, należy go przypisać do dostawcy. Przejdź do **Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawcy** i wybierz dostawcę, który ma zostać przypisany do kalendarza. Następnie na stronie dostawcy na skróconej karcie **Domyślne zamówienia zakupu** przypisz nowy kalendarz za pomocą menu rozwijanego. 

Kalendarz dla dostawcy wskazuje dni, kiedy przyjmuje on składanie zamówień zakupu oraz daty, kiedy może dostarczyć zamówienia do Twojej firmy. W związku z tym daty zamówienia dla zamówień zakupu dla danego dostawcy z kalendarzem zakupu będą datami zdefiniowanymi w kalendarzu jako otwarte. Daty dostarczenia tych zamówień będą również dniami otwartymi i dlatego będą miały wpływ na czas realizacji zakupionego towaru. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Definiowanie czasu realizacji dla zakupionego towaru

Aby określić czasu realizacji zakupu (i czy należy brać pod uwagę tylko dni robocze) dla towaru, należy przejść na stronę domyślnych ustawień zamówienia dla produktu, która znajduje się w **Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty** i wybierz **Domyśle ustawienia zamówienia**. 

> [!Note]
> **Dni robocze** w czas realizacji zakupu wskazują dni robocze dostawcy. Na przykład kalendarz dla dostawy tylko we wtorki z czasem realizacji 10 dni oraz zaznaczonym polem wyboru dni roboczych oznacza, że dostarczenie towary zajmie 10 tygodni (10 wtorków).
W związku z tym w większości przypadków nie zaleca się wybierania dni roboczych dla czasów realizacji zamówień zakupu.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Definiowanie czasu realizacji ze strony umów handlowych

Planowanie główne można skonfigurować do uwzględnienia wszystkich umów handlowych dla dostawców. Umowy handlowe są cenami stałymi lub umowami rabatu, które są ustawione dla jednego lub więcej odbiorców lub dostawców dla sprzedaży lub zakupu pojedynczych lub wielu produktów. Przejdź do **Planowanie główne > Ustawienia > Parametry planowania głównego** i na kartę **Zamówienia planowane** i zaznacz opcję **Znajdź umowy handlowe**, aby uwzględniać umowy handlowe podczas planowania. Planowanie główne możne wybrać dostawcę z **Minimalny czas realizacji** lub **Najniższa cena jednostkowa**.

### <a name="calendar-for-a-warehouse"></a>Kalendarz dla magazynu
Można przypisać kalendarz do magazynu, aby wskazać otwarte daty przyjęcia i wysyłki. Jeśli nie ma kalendarza przypisanego do magazynu, zakłada się, że wszystkie dni są otwarte. 

> [!Note]
> Przypisanie kalendarza do magazynu tranzytowego nie ma wpływa na nic. Magazyny tranzytowe są używane do obsługi zamówień przeniesienia. Odpowiednie daty wysyłki lub przyjęcia dla zamówień są definiowane przez otwarte dni w magazynie „Źródłowym” i magazynie „Docelowym” oraz przez kalendarz metody dostawy.

#### <a name="closed-for-pickup-policy"></a>Zamknięte dla zasady pobrania
Aby wskazać, że magazyn jest otwarty do przyjęcia, ale odbiór jest niemożliwy, można użyć opcji **Zamknięte dla zasady pobrania** w kalendarzu magazynu. Dotyczy to również pobrań odbiorcy. 

### <a name="transport-calendar"></a>Kalendarz transportu 
Aby wskazać daty dostępnych dla wysyłki zamówień przeniesienia z **magazynu źródłowego**, można przypisać **kalendarz transportu**. Można zdefiniować kalendarz transportu według metody dostawy lub według metody dostawy z magazynu. Kalendarz transportu ustawia się w **Sprzedaż i marketing > Ustawienia > Dystrybucja > Metody dostawy**. Wybierz metodę dostawy i kliknij przycisk **Kalendarz transportu**.

Wiersz można utworzyć dla każdego magazynu i metoda dostawy, gdzie kalendarz jest dodawany do kolumny **Kalendarz transportu**. Określi on kalendarz transportu, który będzie stosowany podczas wysyłki towarów z magazynu przy użyciu danej metody dostawy. Aby zastosować kalendarz transportu do wszystkich wysyłek przy użyciu danej metody dostawy, wiersz można utworzyć bez określenia magazynu.  Wpłynie to na wszystkie wysyłki używające danej metody dostawy, bez względu na magazyn. 

Jeśli nie ma przypisanego kalendarza transportu, zakłada się, że wszystkie dni są otwarte dla transportu.

### <a name="calendar-for-a-customer"></a>Kalendarz dla odbiorcy
Aby wskazać daty, kiedy odbiorca może przyjąć dostawy, można przypisać kalendarz przyjęć dla odbiorcy. Jeśli nie ma kalendarza przypisanego do odbiorcy, zakłada się, że odbiorca może odbierać zamówienia we wszystkie dni. Wpłynie to na datę przyjęcia w wierszach zamówienia sprzedaży. Wybranie daty w wierszach zamówienia sprzedaży, która nie jest „otwarta” w kalendarzu odbiorcy, spowoduje, że system wskaże nieprawidłową datę przyjęcia. 

Należy pamiętać, że można dla każdego odbiorcy można dodać tylko jeden kalendarz. Jeśli chcesz dodać kalendarz dla każdego adresu odbiorcy, możesz utworzyć jednego odbiorcę dla każdego adresu i następnie przypisać do nich odpowiedni kalendarz. 

Na żądaną datę przyjęcia w wierszach zamówienia sprzedaży wpływa kalendarz odbiorcy i metoda kontroli daty dostawy. Można znaleźć więcej informacji o sposobie obliczania najwcześniejszej daty dostawy w temacie [Zobowiązanie do zamówienia.](/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Kalendarz wysyłek dla firmy
Aby wskazać daty, kiedy firma może wysłać towary, można ustawić kalendarz w **Administrowanie organizacją > Organizacje > Firmy**. Wybierz firmę i dodaj kalendarz na karcie **Handel zagraniczny i logistyka** w polu **Kalendarz wysyłek**. Kalendarz wysyłek będzie działać jako źródło wartości domyślnych dla wszystkich kalendarzy magazynu w firmie. 

## <a name="how-calendars-affect-dates-in-planning"></a>Jak kalendarze wpływają na daty w planowaniu

### <a name="order-date-of-a-planned-purchase-order"></a>Data zamówienia w planowaniu zamówienia zakupu 
Data zamówienia w planowaniu zamówienie zakupu wskazuje datę, kiedy złożono zamówienie. Jest otwarta data w zarówno w kalendarzu dostawcy, jak i grupy zapotrzebowania. Czasami dostawcy potrzebują kilku dni do odebrania zamówienia zakupu do wysłaniem towarów. Te daty są oznaczone za pomocą dni marginesu dostawcy. Jednak jeśli zakupiony towar jest przypisany do grupy zapotrzebowania z dniami marginesu, te dni marginesu zostaną zastąpione dniami marginesu dostawcy.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Data dostawy w planowaniu zamówienia zakupu
Data przyjęcia zakupu wskazuje datę, kiedy odbierzesz towary. Będzie to data otwarta w kalendarzu. Kalendarz, który będzie brany pod uwagę w celu wskazania dni. kiedy zamówienie może zostać odebrane, jest następujący w kolejności od najwyższego do najniższego priorytetu: 
1. Kalendarz dostawcy
1. Kalendarz grupy zapotrzebowania
1. Kalendarz magazynu dla magazynu przyjęcia

Kalendarz grupy zapotrzebowania można skonfigurować na różnych stronach i priorytet będzie ustalany w następującej kolejności:
1. Grupy zapotrzebowania na towar na stronie **Zapotrzebowanie na towary**
1. Grupy zapotrzebowania na towar na stronie **szczegóły zwolnionych produktów**
1. Domyślna grupa zapotrzebowania na towar na stronie **Parametry planowania głównego**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Data wysyłki w planowanym zamówieniu przeniesienia
Podczas tworzenia zamówienia przeniesienia między dwoma magazynami, data wysyłki oraz data przyjęcia znajdują się w nagłówku zamówienia przeniesienia, wraz z magazynem „Źródłowym” a „Docelowym”. Różnica między tymi dwiema datami polega na oczekiwanym czasie transportu (w dniach) między magazynami.

Data wysyłki planowanego zamówienia przeniesienia wskazuje datę wysyłania towarów z magazynu „Źródłowego”. Kalendarze używane do określenia dostępnej daty wysyłki są wyświetlane według priorytetów: 
1. Kalendarz dla magazynu „Źródłowego”
1. Kalendarz grupy zapotrzebowania (zobacz zamówienie powrotu dla tego kalendarza powyżej) Jeśli ustawiony jest kalendarz magazynu, data wysyłki będzie otwartą datą w kalendarzu. Jeśli nie ma ustawionego kalendarza magazynu, zostanie użyty kalendarz grupy zapotrzebowania. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Data przyjęcia w planowanym zamówieniu przeniesienia
Data przyjęcia dla zamówienia przeniesienia wskazuje datę odebrania towarów w magazynie „Docelowym”.

Kalendarze używane do określenia daty przyjęcia zostały wymienione poniżej w kolejności według priorytetu: 
1. Kalendarz grupy zapotrzebowania 
1. Kalendarz magazyn magazynu „Docelowego” Jeśli jest ustawiony kalendarz zapotrzebowania, data przyjęcia będzie otwartą datą w kalendarzu. Jeśli nie ma ustawionego kalendarza grupy zapotrzebowania, zostanie użyty kalendarz magazynu. 

Podczas znajdowania dat wysyłki i przyjęcia dla planowanego przeniesienia pod uwagę będą brane również marginesy ustawione przez użytkownika dla wysyłki i przyjęcia. 

## <a name="using-calendars-in-master-planning"></a>Używanie kalendarzy w planowaniu głównym

### <a name="assignment-of-scm-calendars"></a>Przypisanie kalendarzy SCM
Należy ustawić kalendarzy do identyfikowania dni roboczych firmy. Najlepszą metodą implementacji jest ustawienie kalendarza dla każdego elementu z innymi dniami roboczymi. Inaczej mówiąc, chodzi o wszystkie kalendarze zewnętrzne (odbiorcy, dostawcy) i wszystkie kalendarze wewnętrzne (magazynu, grupy zapotrzebowania i metody dostawy) związane z firmą

### <a name="recommendation-on-warehouse-calendars"></a>Zalecenie dotyczące kalendarzy magazynu
Zaleca się używanie jednego kalendarza na magazyn celem uwzględnienia specyficznych zmian mających wpływ tylko na danych magazyn. Na przykład dwa lub więcej magazynów może mieć te same dni robocze, ale inne zasady pobierania. W takim przypadku kalendarz dla wszystkich magazynów z odpowiednimi zasadami pobrania jest najlepszą implementacją, która umożliwia systemowi uwzględnienie najważniejszych dat dla planowanych zamówień zakupu, produkcji i przeniesienia. Jeśli nie ustawiono żadnych kalendarzy dla magazynu, kalendarz firmy może być używany jako źródło wartości domyślnych dla kalendarza magazynu. 

### <a name="recommendation-of-coverage-group-calendars"></a>Zalecenie dotyczące kalendarzy grupy zapotrzebowania
W kontekście kalendarza grupy zapotrzebowania należy wziąć pod uwagę, że jest on nadrzędny względem dat przyjęcia w planowaniu głównym. Dlatego zaleca się używanie go z rozwagą. Jest on szczególnie użyteczny, kiedy uzupełnianie zapasów ma się odbywać w konkretne dni tygodnia. 

### <a name="updating-scm-related-calendars"></a>Aktualizowanie kalendarzy związanych z SCM
Wszystkie odpowiednie kalendarze powinny być przypisywane w ich odpowiednich miejscach (dostawca, odbiorca, magazyn, tryb dostawy lub grupa zapotrzebowania), ale równie ważne jest ich aktualizowanie zgodnie z zachodzącymi zmianami. System określi daty zamówień produkcji, przeniesienia, zakupu i sprzedaży w zależności od kombinacji przypisanych kalendarzy. Najlepszym rozwiązaniem jest wyjaśnienie, kto odpowiada za przydzielanie i aktualizowanie kalendarzy w odpowiadających im obszarach. W przypadku awarii lub innych nadzwyczajnych zmiany w daniach roboczych należy konieczne zaktualizować kalendarze zgodnie z tymi okolicznościami. Wszystkie zadania, które zależą od kalendarzy, takie jak planowanie główne i planowanie produkcji, muszą zostać uruchomiony ponownie po wykonaniu aktualizacji kalendarzy. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]