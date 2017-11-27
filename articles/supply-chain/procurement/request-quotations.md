---
title: Zapytania ofertowe
description: "W tym temacie omówiono funkcjonalność zapytań ofertowych (ZO), które organizacje wystawiają, kiedy muszą kupić towary lub usługi, a chcą otrzymać konkurencyjne oferty od kilku dostawców."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 495e28a5d61d8c0c3ccfbf731e693f2b5e2e7892
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="request-for-quotations-rfqs"></a>Zapytania ofertowe

[!include[banner](../includes/banner.md)]


W tym temacie omówiono funkcjonalność zapytań ofertowych (ZO), które organizacje wystawiają, kiedy muszą kupić towary lub usługi, a chcą otrzymać konkurencyjne oferty od kilku dostawców. W ZO dostawcy są proszeni o podanie cen i terminów dostaw dla ilości towarów określonych przez użytkownika. Można również poprosić dostawców, aby określili, czy są jakieś dodatkowe opłaty, takie jak koszty wysyłki, albo zniżki za duże zamówienia lub szybką zapłatę faktury.

Proces zapytania ofertowego obejmuje następujące zadania:

-   tworzenie i wysyłanie ZO do jednego lub większej liczby dostawców,
-   Odbieranie i rejestrowanie odpowiedzi na ZO (oferty).
-   Przenoszenie zaakceptowanych ofert do zamówienia zakupu, umowy zakupu lub zapotrzebowania na zakup.

Na poniższej ilustracji przedstawiono przegląd procesu ZO.  

[![Proces zapytań ofertowych](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

ZO można tworzyć z zamówień planowanych lub zapotrzebowań na zakup albo wprowadzać je ręcznie. Tworzone ZO jest nazywane sprawą ZO i jest to bazowy dokument używany do wystawiania ZO dla każdego dostawcy. Po przygotowanie sprawy ZO i dodaniu dostawców kliknij przycisk **Wyślij** w sprawie ZO. Arkusz ZO jest tworzony dla każdego dostawcy, któremu wysłano ZO. Można skonfigurować ustawienia zarządzania drukowaniem dla akcji wysyłania, aby wydrukować raport dla każdego dostawcy w celu archiwizowania, lub wysłać raporty na adresy e-mail dostawców. Ponadto arkusz ZO dla każdego dostawcy może służyć do generowania raportu, który można wysłać lub później ponownie wysłać do dostawcy. Można również skonfigurować akcję wysłania, aby wygenerować arkusz odpowiedzi, który mogą wypełniać dostawcy.  

Jeśli trzeba zmienić ZO po jego wysłaniu, można wysłać ponownie ZO do dostawców.  

Po otrzymaniu ofert, należy wprowadzić je na stronie **Odpowiedzi na zapytanie ofertowe**. Jeśli wybierzesz opcję **Kopiuj dane do odpowiedzi**, dane jak ilość i daty ze sprawy ZO zostaną skopiowane do odpowiedzi. Można zmienić te dane, tak aby odzwierciedlały ofertę dostawcy.  

Jeśli w przypadku określonego dostawcy wymagana jest druga iteracja odpowiedzi, kliknij **zwrot** na stronie **Odpowiedź na zapytanie ofertowe**. Akcja zwrotu tworzy nowy arkusz i raport, który będzie można wydrukować, archiwizować i wysyłać zgodnie z ustawieniami zarządzania drukowaniem.  

Po dodaniu do sprawy ZO kryteriów punktowania, odpowiedzi na ZO będą miały panel punktowania, w którym można wprowadzać oceny. Łączny wynik będzie wyświetlany podczas porównywania odpowiedzi na stronie **porównania odpowiedzi**, gdzie można porównać również inne dane dotyczące odpowiedzi, takie jak cena wiersza, data dostawy i łączna cena.  

Po podjęciu decyzji dotyczących oferty lub częściowej oferty, można je przyjąć i odrzucić pozostałe. Generowane są arkusze przyjęcia, odrzucenia i odpowiednie raporty. Zostaną one wydrukowane, zarchiwizowane i wysłane na podstawie ustawień zarządzania drukowaniem. Po zaakceptowaniu oferty lub określonych wierszy oferty aktualizowane są zamówienie zakupu, umowa zakupu lub zapotrzebowanie na zakup, w zależności od typu zakupu ZO. Można utworzyć umowę handlową, której można następnie użyć w odpowiedziach, bez względu na to, czy je odrzucasz czy akceptujesz.  

Stan ZO pojawiają się w nagłówku ZO i zależy od stanu wierszy ZO. Ten stan wskazuje zakres, do którego zostało przetworzone ZO. Każde ZO ma dwie wartości stanu: najniższy i najwyższy. Najniższy stan jest najmniej zaawansowanym etapem wiersza ZO, a najwyższy stan jest najbardziej zaawansowanym etapem wiersza w ZO. Na przykład, jeśli najmniej zaawansowany stan w ZO jest dla wiersza, który został utworzony, najniższy stan dla ZO to **Utworzone**. Jeśli najbardziej zaawansowany stan w ZO jest dla wiersza, który został wysłany do dostawców, najwyższy stan dla ZO to **Wysłane**. Stany są automatycznie aktualizowane w trakcie przetwarzania ZO.  

Można przeglądać najniższe i najwyższe stany nagłówka ZO na stronie **Wszystkie zapytania ofertowe**. Można przeglądać najniższe i najwyższe stany nagłówka ZO na stronie karcie **Wiersze** na stronie **Zapytania ofertowe**.  

Sekwencja stanów dla przetwarzania ZO jest następująca:

1.  **Utworzone**
2.  **Wysłane**
3.  **Odebrane**
4.  **Zaakceptowane**/**Anulowane**/**Odrzucone**

Stany zostaną opisane bardziej szczegółowo w kolejnych rozdziałach tego tematu.

## <a name="setting-up-rfq-functionality"></a>Konfigurowanie funkcji ZO
Aby można było tworzyć sprawy ZO, należy skonfigurować informacje ZO na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu sprawy ZO można określić wartości domyślne, które są kopiowane do ZO. Można określić następujące wartości domyślne:

-   Typ zakupu nowych ZO: **Zamówienie zakupu** lub **Umowa zakupu**.
-   Ustawienia daty i godziny ważności.
-   Informacje o dostawie i warunki płatności.
-   Pola, które powinny znajdować się w odpowiedzi na ZO.

Można zastąpić te wartości dla określonej sprawy ZO. Należy także skonfigurować proces poprawki. W ramach tej konfiguracji można włączyć pole blokowania. Gdy blokowanie pól jest włączone, pracownik działu zaopatrzenia, który chce zmienić ZO musi najpierw kliknąć opcję **Utwórz** w sekcji **Poprawka** karty **Oferta**. Po zaktualizowaniu ZO o poprawkę pracownik działu zaopatrzenia musi ukończyć proces, klikając przycisk **Finalizuj**. Akcja **Finalizuj** generuje wiadomość e-mail powiadamiającą dostawcę o poprawionym ZO. Szablon powiadomienia e-mail przesyłanego do dostawców można wybrać na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu szablon może zawierać następujące tokeny wymiany:

-   %Przyczyna zwrotu oferty%
-   %Przyczyna sporządzenia poprawki%
-   %Poprawka przygotowana przez%
-   %Firma%

Tokeny %Przyczyna zwrotu oferty% i %Przyczyna sporządzenia poprawki% zastępuje tekst, który pracownik działu zakupów może wpisać po zakończeniu poprawki w **kreatorze poprawek**. Wartości tokenów %poprawki przygotowane przez% i %firma% są automatycznie pobierane z ZO.  

Jeśli chcesz użyć kodów przyczyn w odpowiedzi na ZO, aby wskazać, dlaczego oferta została zaakceptowana lub odrzucona, musisz ustawić te kody na stronie **przyczyny dotyczące dostawcy**.  

Na stronie **ustawienia formularza** w module Zaopatrzenie i sourcing można skonfigurować wygląd drukowanych lub przechowywanych dokumentów ZO. 

**Uwaga:** W konfiguracji dla sektora publicznego wszelkie zmiany wprowadzone w ZO, które już zostało wysłane, wymagają stosowania procesu poprawki. Po wysłaniu zapytania ofertowego pola są blokowane, więc kliknięcie przycisku **Utwórz** w celu użycia procesu poprawki jest obowiązkowym krokiem dla wprowadzenia zmian do zapytania ofertowego.
To zachowanie jest kontrolowane za pomocą parametru blokowania pól **Zablokuj ZO, gdy zostaną wysłane** znajdującego się w oknie **Parametry modułu Zaopatrzenie i sourcing**. Ten parametr ma ustawioną wartość **Tak** i w konfiguracji dla sektora publicznego jest to ustawienie domyślne, którego nie można zmienić. Oznacza to, że o ile proces poprawki może być obsługiwany ręcznie w konfiguracji dla sektora prywatnego, w sektorze publicznym obowiązuje proces poprawki z blokowaniem pól po wysłaniu zapytania ofertowego.

Gdy tworzysz ZO dla zamówienia zakupu i dodajesz towar magazynowy do ZO, zostaje wygenerowana transakcja magazynowa, która ma stan przyjęcia **Otrzymanie oferty**. Tylko wiersze ZO z tym stanem są uwzględniane podczas korzystania z planu głównego do obliczania dostaw. Aby uwzględniać wiersze ZO jako oczekiwane przyjęcia planu głównego, należy skonfigurować to zachowanie w ustawieniach planowania głównego.  

Jako menedżer lub agent ds. zakupów możesz tworzyć i obsługiwać typy zdobywania zamówień tak, aby spełniały wymogi zamówień dla danej organizacji. Każdy typ zdobywania zamówień może mieć nowe metody punktowania. Metody punktowania zawierają szereg kryteriów, których można używać podczas oceny ofert. Należy skonfigurować typy zdobywania zamówień, metody punktowania oraz kryteria określania wyników na stronach **Typ zdobywania zamówień** i **Metoda punktowa**.

## <a name="creating-and-sending-an-rfq"></a>Tworzenie i wysyłanie ZO
Utwórz ZO, wybierz dostawców, od których chcesz uzyskać oferty dla ZO, a następnie wyślij ZO do dostawców. Można używać zarządzania drukowaniem do kierowania raportu ZO i odpowiadania na raporty arkusza do preferowanego miejsca docelowego.  

ZO można tworzyć dla zakupu, który ma typ **Zamówienie zakupu** lub **Umowa zakupu**.  

Jeśli ZO jest generowane na podstawie zapotrzebowania na zakup, typ **Zapotrzebowanie na zakup** jest przypisywany automatycznie. Nie można ręcznie utworzyć ZO typu **Zapotrzebowanie na zakup**. Jeśli ZO ma typ **Zamówienie zakupu**:

-   Podczas tworzenia wierszy ZO generowane są transakcje magazynowe, które mają stan przyjęcia **Przyjęcie oferty**.
-   Po zaakceptowaniu oferty generowane jest zamówienie zakupu.

Jeśli ZO ma typ **Umowa zakupu**:

-   ZO jest używane dla umowy zakupu do zakupu ilości lub wartości produktu w określonym czasie. Należy wybrać zakres dat, którego dotyczy umowa zakupu i nazwisko osoby, która zarządza umową.
-   Po zaakceptowaniu oferty generowana jest umowa zakupu.

Można utworzyć ZO z zapotrzebowania na zakup tylko wtedy, gdy zapotrzebowanie na zakup ma stan **W trakcie przeglądu**, a następne zadania przepływu pracy jest przypisane do użytkownika. Wiersze zapotrzebowania na zakup są aktualizowane automatycznie, gdy użytkownik akceptuje wiersze z odpowiedzi na ZO (ofert) otrzymywanych od dostawców. W trakcie przetwarzania zapytania ofertowego nie można sporządzić, odrzucić, zatwierdzić czy wykonywać żadnych innych działań dotyczących zapotrzebowania na zakup.  

Po utworzeniu ZO można wybrać określony typ zdobywania zamówień. Typ zdobywania zamówień określa zestaw kryteriów punktowania służący do odpowiedzi na ZO.  

Kwestionariusz można dodać do sprawy ZO. Będzie on widoczny we wszystkich odpowiedziach po wysłaniu ZO.  

Istnieją trzy sposoby wyboru dostawców dodawanych do sprawy ZO:

-   Dodawanie dostawców po kolei.
-   Wyszukiwanie wszystkich dostawców spełniających określone kryteria.
-   Automatyczne dodawanie wszystkich dostawców, którzy zostali zatwierdzeni dla kategorii zaopatrzenia używanych w wierszach ZO.

Gdy sprawa ZO jest gotowa, kliknij przycisk **Wyślij**. Akcja Wyślij tworzy nowe arkusze i raporty, które będzie można drukować, archiwizować i wysyłać zgodnie z ustawieniami zarządzania drukowaniem.  

Jeśli zaznaczono pola wyboru **Użyj dostawcy w celu ponownego obliczenia cen** i **Użyj informacji o towarze specyficznym dostawcy** na stronie **Wysyłanie zapytania ofertowego** po wysłaniu zapytania do dostawców, niektóre informacje właściwe dla dostawcy są wprowadzane automatycznie. Można zmienić te informacje na stronie **Odpowiedź na zapytanie ofertowe**.  

W poniższej tabeli przedstawiono, jak zmienia się stan ZO przy tworzeniu ZO i wysyłaniu go do dostawców.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Akcja**                         | **Najniższy stan nagłówka ZO** | **Najwyższy stan nagłówka ZO**                   | **Najniższy stan wiersza ZO** | **Najwyższy stan wiersza ZO** |
| Utwórz nagłówek i wiersz ZO.    | Utworzone                      | Utworzone                                         | Utworzone                    | Utworzone                     |
| Wysyłanie ZO do określonego dostawcy. | Wysłano                         | Wysłano                                            | Wysłano                       | Wysłano                        |
| Dodwanie nowego dostawcy.                | Utworzone                      | Wysłane (ZO zostało wysłane do tylko jednego dostawcy.) | Utworzony                    | Wysłano                        |
| Wysyłanie ZO do drugiego dostawcy. | Wysłano                         | Wysłano                                            | Wysłano                       | Wysłano                        |

**Uwaga:** Można dodać kolejnych dostawców do ZO w dowolnym momencie, a najniższe i najwyższe stany zmieniają się, aby odzwierciedlić nowych dostawców, którzy zostali dodani. Na przykład, jeśli otrzymano oferty od wszystkich dostawców, a co najmniej jeden wiersz oferty zaakceptowano, najniższy stan w nagłówku ZO to **Odrzucono**, a najwyższy stan to **Zaakceptowany**. Po dodaniu nowego dostawcy, najniższy stan w dowolnym wierszu zostanie zmieniony na **Utworzono**. Dlatego najniższy stan w nagłówku ZO zmienia się na **Utworzono**, a najwyższy stan pozostaje **Zaakceptowane**.

## <a name="amending-an-rfq"></a>Zmienianie ZO
Czasami trzeba zmienić ZO, które zostało już wysłane. Na przykład taka sytuacja może wystąpić, gdy zmienią się terminy dostawy lub trzeba dodać produkty albo zmienić ilości produktów. Proces zmiany można skonfigurować w taki sposób, by był bardziej lub mniej restrykcyjny.  

W przypadku metody bardziej restrykcyjnej, trzeba kliknąć przycisk **Utwórz** w sprawie ZO, aby uruchomić proces zmian. Inaczej pola w sprawie ZO nie są dostępne do edycji. Po wprowadzeniu zmian należy kliknąć **Finalizuj**. Następnie redaguje się powiadomienia wysyłane e-mailem do dostawców i informujące ich o wprowadzonych zmianach. Zaktualizowany raport ZO z informacją o zmianie jest automatycznie dołączany do wiadomości.  

W przypadku mniej restrykcyjnej metody wprowadzania zmian, nie trzeba tworzyć zmiany przed zmodyfikowaniem pól w sprawie ZO, które zostało już wysłane. Trzeba jednak ręczne wpisać informację o zmianie na ZO.

## <a name="receiving-and-registering-rfq-replies"></a>Odbieranie i rejestrowanie odpowiedzi na ZO
Podczas wysyłania ZO, automatycznie jest generowany arkusz odpowiedzi. Po otrzymaniu odpowiedzi (oferty) na ZO w arkuszu odpowiedzi na ZO specyficzne dla dostawcy trzeba wprowadzić informacje od każdego dostawcy. Po dodaniu kryteriów punktowania można przydzielić odpowiedziom punkty. Następnie porównuje się oferty dostawców i ocenia je według takich kryteriów oceniania, jak najlepsza cena całkowita lub najlepszy całkowity czas dostawy.  

Jeśli do sprawy ZO dołączony jest kwestionariusz, trzeba ręcznie wpisać odpowiedzi na pytania w arkuszu odpowiedzi.  

Jeśli trzeba wprowadzić wiersze alternatywne, a sprawa ZO to umożliwia, na skróconej karcie **Wiersze oferty zakupu** kliknij **Dodaj wiersz**. Następnie wprowadź informacje o produkcie, takie jak ilość, cena i rabaty, kod towaru lub kategoria zaopatrzenia.  

Jeśli została wprowadzona odpowiedź, ale wymagana jest nowa oferty od dostawcy, można ponownie wysłać ZO. Spowoduje to wygenerowanie nowego arkusza i raportu, za pomocą którego można poprosić dostawcę o wprowadzenie zmian.  

Podsumowanie wszystkich ZO i ich stanów odpowiedzi jest widoczne na stronie **Kolejne czynności dla zapytania ofertowego**.  

W poniższej tabeli przedstawiono, jak zmienia się stan ZO podczas odbierania ofert i rejestrowania informacji w arkuszu odpowiedzi na ZO.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Akcja**                                     | **Najniższy stan oferty** | **Najwyższy stan oferty** | **Najniższy stan nagłówka ZO** | **Najwyższy stan nagłówka ZO** | **Najniższy stan wiersza ZO** | **Najwyższy stan wiersza ZO** |
| Rejestrowanie oferty jednego dostawcy i zapisywanie jej.        | Wysłano                  | Otrzymane               | Wysłano                         | Otrzymane                      | Wysłano                       | Otrzymane                    |
| Rejestrowanie oferty drugiego dostawcy i zapisywanie jej. | Odebrano              | Odebrano               | Odebrano                     | Odebrano                      | Odebrano                   | Odebrano                    |

**Uwaga:** Jeśli zwrócisz ofertę dostawcy w celu dodatkowych negocjacji, najniższy i najwyższy stan nie zmienia się i jest następujący: **Otrzymano**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Akceptowanie i odrzucenia ofert i przenoszenie zaakceptowanych ofert do dokumentów przesyłanych od dostawcy do odbiorcy

Po znalezieniu najlepszej oferty, takiej jak oferta, która z najlepszą ceną całkowitą, należy zaakceptować ofertę. Stan odpowiedzi na ZO dla tego dostawcy jest aktualizowany do **Zaakceptowana**. Po zaakceptowaniu oferty lub określonych wierszy oferty zamówienie zakupu lub umowa zakupu są generowane automatycznie i można odrzucić oferty innych dostawców.  

Po zaakceptowaniu odpowiedzi na ZO typu **Zapotrzebowanie na zakup**, wiersze takiej odpowiedzi uaktualnią wiersze zapotrzebowania zakupu następującymi informacjami:

-   Cena jednostkowa
-   Procent rabatu
-   Kwota rabatu
-   Opłaty od zakupu
-   Opłaty za wierszy
-   Dostawca
-   numer zewnętrzny,
-   Zewnętrzny opis

Po uzyskaniu odpowiedzi można dodać kod przyczyny wyjaśniającej, dlaczego oferta została przyjęta lub odrzucona.  

Można zaakceptować niektóre wiersze oferty i odrzucić inne. Można również zaakceptować wiersze pochodzące od różnych dostawców. Trzeba pamiętać, że w przypadku zaakceptowania niektórych wierszy pojawi się monit o odrzuceniu wszystkich pozostałych. Aby zaakceptować te pozostałe wiersze, trzeba kliknąć **Anuluj** po pojawieniu się monitu.  

W poniższej tabeli przedstawiono, jak zmienia się stan ZO w przypadku akceptowania lub odrzucania ofert od dostawców.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Akcja**              | **Najniższy stan oferty** | **Najwyższy stan oferty** | **Najniższy stan nagłówka ZO** | **Najwyższy stan nagłówka ZO** | **Najniższy stan wiersza ZO** | **Najwyższy stan wiersza ZO** |
| Zaakceptowanie jednej z ofert. | Otrzymane              | Zaakceptowany               | Odebrano                     | Zaakceptowany                      | Odebrano                   | Zaakceptowany                    |
| Odrzucenie innych ofert.  | Odrzucono              | Zaakceptowany               | Odrzucono                     | Zaakceptowany                      | Odrzucono                   | Zaakceptowany                    |






