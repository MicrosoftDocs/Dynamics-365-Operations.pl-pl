---
title: Zapytanie ofertowe (ZO)
description: "W tym temacie opisano zapytania ofertowe (ZO). Organizacje wystawiają zapytania ofertowe (ZO), kiedy chcą uzyskać od kilku dostawców konkurencyjne oferty na produkty i usługi, które muszą kupić."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 42ab7beb8a269cd37fd9100385bd302e4945c1e0
ms.contentlocale: pl-pl
ms.lasthandoff: 12/14/2017

---

# <a name="requests-for-quotation-rfqs"></a>Zapytanie ofertowe (ZO)

[!include[banner](../includes/banner.md)]

W tym temacie opisano zapytania ofertowe (ZO). Organizacje wystawiają zapytania ofertowe (ZO), kiedy chcą uzyskać od kilku dostawców konkurencyjne oferty na produkty i usługi, które muszą kupić. W ZO dostawcy są proszeni o podanie cen i terminów dostaw dla ilości towarów określonych przez użytkownika. Można również poprosić dostawców, aby określili, czy są jakieś dodatkowe opłaty, takie jak koszty wysyłki, albo zniżki za duże zamówienia lub szybką zapłatę faktury.

Proces ZO składa się z następujących zadań:

1. Utworzenie i wysyłanie ZO do jednego lub większej liczby dostawców.
2. Otrzymywanie i rejestrowanie odpowiedzi na ZO (ofert).
3. Przenoszenie zaakceptowanych ofert do zamówienia zakupu, umowy zakupu lub zapotrzebowania na zakup.

Na poniższej ilustracji przedstawiono przegląd procesu ZO.

[![Proces RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

ZO można tworzyć z zamówień planowanych lub zapotrzebowań na zakup albo wprowadzać je ręcznie. Utworzone ZO jest nazywane sprawą ZO. Sprawa ZO to podstawowy dokument używany do wysyłania ZO do każdego dostawcy.

Po przygotowaniu sprawy ZO i dodaniu dostawców wybierz opcję **Wyślij** w sprawie ZO. Dla każdego dostawcy, do którego wysłano ZO generowany jest arkusz ZO. Można skonfigurować ustawienia zarządzania drukowaniem dla akcji wysyłania, aby wydrukować raport dla każdego dostawcy w celu archiwizowania, lub wysłać raporty na adresy e-mail dostawców. Ponadto arkusz ZO dla każdego dostawcy może służyć do generowania raportu, który można wysłać lub później ponownie wysłać do dostawcy. Można również skonfigurować akcję wysłania, aby wygenerować arkusz odpowiedzi, który mogą wypełniać dostawcy.

W tym temacie opisano proces obsługi ZO, gdy nie jest używana współpraca z dostawcą. Jeśli system jest skonfigurowany do współpracy z dostawcami, dostawcy mogą wprowadzić oferty bezpośrednio w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Aby uzyskać więcej informacji, zobacz [Współpraca z odbiorcami przy użyciu modułu Współpraca z dostawcami](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Jeżeli po wysłaniu wymagana jest zmiana ZO, po zakończeniu można ponownie wysłać ZO do dostawców, korzystając z dwóch akcji zmian: Utwórz i Finalizuj.

Po otrzymaniu ofert w wiadomości e-mail, należy wprowadzić je na stronie **Odpowiedzi na zapytanie ofertowe**. Jeśli wybierzesz opcję **Kopiuj dane do odpowiedzi**, dane jak ilość i daty ze sprawy ZO zostaną skopiowane do odpowiedzi. Można zmienić te dane, tak aby odzwierciedlały ofertę dostawcy.

Jeśli w przypadku danego dostawcy wymagana jest druga iteracja odpowiedzi, wybierz opcję **Zwrot** na stronie **Odpowiedź na zapytanie ofertowe**. Akcja zwrotu tworzy nowy arkusz i raport, który będzie można wydrukować, archiwizować i wysyłać zgodnie z ustawieniami zarządzania drukowaniem.

Po dodaniu do sprawy ZO kryteriów punktowania, odpowiedzi na ZO będą miały panel punktowania, w którym można wprowadzać oceny. Całkowity wynik będzie widoczny po porównaniu odpowiedzi na stronie **Porównaj odpowiedzi**. Na tej stronie można także porównać inne dane odpowiedzi, takie jak cena wiersza, data dostawy i cena łączna.

Po wybraniu oferty lub częściowej oferty, można je zaakceptować i odrzucić pozostałe. Arkusze przyjęcia, odrzucenia i odpowiednie raporty zostaną wygenerowane i wydrukowane, oraz wydrukowane, zarchiwizowane i wysłane zgodnie z ustawieniami zarządzania drukowaniem. Po zaakceptowaniu oferty lub określonych wierszy oferty w zależności od typu zakupu ZO tworzona jest umowa zakupu lub zamówienie zakupu lub aktualizowane jest zapotrzebowanie na zakup. Można utworzyć umowę handlową, której można następnie użyć w odpowiedziach, bez względu na to, czy je odrzucasz czy akceptujesz.

Stan ZO pojawiają się w nagłówku ZO i zależy od stanu wierszy ZO. Ten stan wskazuje postęp przetworzenia ZO. Każde ZO ma dwie wartości stanu: najniższy i najwyższy. Najniższy stan jest najmniej zaawansowanym etapem wiersza ZO, a najwyższy stan jest najbardziej zaawansowanym etapem wiersza w ZO. Na przykład, jeśli najmniej zaawansowany stan w ZO jest dla wiersza, który został utworzony, najniższy stan dla ZO to **Utworzone**. Jeśli najbardziej zaawansowany stan w ZO jest dla wiersza, który został wysłany do dostawców, najwyższy stan dla ZO to **Wysłane**. Stany są automatycznie aktualizowane w trakcie przetwarzania ZO.

Można przeglądać najniższe i najwyższe stany nagłówka ZO na stronie **Wszystkie zapytania ofertowe**. Można przeglądać najniższe i najwyższe stany nagłówka ZO na stronie karcie **Wiersze** na stronie **Zapytania ofertowe**.

Sekwencja stanów dla przetwarzania ZO jest następująca:

1. **Utworzone**
2. **Wysłany**
3. **Odebrane**
4. **Zaakceptowane**, **Anulowane** lub **Odrzucone**

Te stany zostaną opisane bardziej szczegółowo w dalszej części tego tematu.

## <a name="setting-up-rfq-functionality"></a>Konfigurowanie funkcji ZO

Aby można było tworzyć sprawy ZO, należy skonfigurować informacje ZO na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu sprawy ZO można określić wartości domyślne, które są kopiowane do ZO. Można określić następujące wartości domyślne:

- Typ zakupu nowych ZO: **Zamówienia zakupu** lub **Umowy zakupu**
- Data i godzina ważności
- Informacje o dostawie i warunki płatności
- Pola, które powinny znajdować się w odpowiedzi na ZO

Można zastąpić te wartości dla określonej sprawy ZO.

Należy także skonfigurować proces poprawki. W ramach tej konfiguracji można włączyć pole blokowania. Gdy blokowanie pól jest włączone, pracownik działu zaopatrzenia, który chce zmienić ZO musi najpierw wybrać opcję **Utwórz** w sekcji **Poprawka** karty **Oferta**. Następnie po zaktualizowaniu ZO o poprawkę pracownik działu zaopatrzenia musi ukończyć proces, wybierając opcję **Finalizuj**. Akcja Finalizuj generuje wiadomość e-mail powiadamiającą dostawcę o poprawionym ZO.

Na stronie **Parametry modułu Zaopatrzenie i sourcing** można wybrać szablon do użycia dla powiadomienia w wiadomości e-wysyłanego do dostawców. Po utworzeniu szablon może zawierać następujące tokeny wymiany:

- %RFQ case%
- %Przyczyna zwrotu oferty%
- %Przyczyna sporządzenia poprawki%
- %Poprawka przygotowana przez%
- %Firma%
- %RFQ case name%
- %ExpiryDateTime%
- %Date%

Tokeny %Przyczyna zwrotu oferty% i %Przyczyna sporządzenia poprawki% zastępuje tekst, który pracownik działu zakupów może wpisać po zakończeniu poprawki w **kreatorze poprawek**. Wartości tokenów %poprawki przygotowane przez% i %firma% są automatycznie pobierane z ZO. Token %Date% jest zastępowany przez bieżącą datę.

Szablon wiadomości e-mail jest także wymagany, jeżeli ZO zostanie anulowane po jego wysłaniu. Ten szablon wiadomości e-mail służy do wysyłania powiadamianie o anulowaniu do osób kontaktowych dostawcy. Szablon należy wybrać na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu szablon może zawierać następujące tokeny wymiany:

- %Reason for cancellation%
- %RFQ case% 
- %RFQ cancelled by%
- %Firma%
- %RFQ case name%
- %Date%

Token %Reason for cancellation% jest zastępowany przez tekst, który specjalista ds. zaopatrzenia może wprowadzić w kreatorze **Anulowanie**. Token %Date% jest zastępowany przez bieżącą datę.

Jeśli chcesz użyć kodów przyczyn w odpowiedzi na ZO, aby wskazać, dlaczego oferta została zaakceptowana lub odrzucona, musisz ustawić te kody na stronie **przyczyny dotyczące dostawcy**.

Na stronie **Ustawienia formularza** w module Zaopatrzenie and sourcing, można skonfigurować wygląd drukowanych lub przechowywanych dokumentów ZO.

> [!NOTE]
> W przypadku konfiguracji sektora publicznego należy użyć procesu zmiany w celu zmiany ZO, które zostało już wysłane. Po wysłaniu ZO pola są blokowane. Dlatego w celu wprowadzenia zmian w ZO należy wybrać opcję **Utwórz**, aby rozpocząć proces zmiany zgodnie z wcześniejszym opisem. Blokowanie jest kontrolowane za pomocą opcji **Zablokuj ZO, gdy zostaną wysłane** na stronie **Parametry modułu Zaopatrzenie i sourcing**. Domyślnie ten parametr ma ustawioną wartość **Tak** i w konfiguracji dla sektora publicznego jest to ustawienie domyślne, którego nie można zmienić. Dlatego, mimo że proces zmiany można obsłużyć ręcznie w konfiguracji sektora niepublicznego, należy go użyć do konfiguracji sektora publicznego.

Gdy tworzysz ZO dla zamówienia zakupu i dodajesz towar magazynowy do ZO, zostaje wygenerowana transakcja magazynowa, która ma stan przyjęcia **Otrzymanie oferty**. Tylko wiersze ZO z tym stanem są uwzględniane podczas korzystania z planu głównego do obliczania dostaw. Aby uwzględniać wiersze ZO jako oczekiwane przyjęcia planu głównego, należy skonfigurować to zachowanie w ustawieniach planowania głównego.

Jako menedżer lub agent ds. zakupów możesz tworzyć i obsługiwać typy zdobywania zamówień tak, aby spełniały wymogi zamówień dla danej organizacji. Każdy typ zdobywania zamówień można powiązać z metodą punktowania. Metody punktowania zawierają szereg kryteriów, których można używać podczas oceny ofert. Należy skonfigurować typy zdobywania zamówień, metody punktowania oraz kryteria określania wyników na stronach **Typ zdobywania zamówień** i **Metoda punktowa**.

## <a name="creating-and-sending-an-rfq"></a>Tworzenie i wysyłanie ZO

Utwórz ZO, wybierz dostawców, od których chcesz uzyskać oferty dla ZO, a następnie wyślij ZO do dostawców. Można używać zarządzania drukowaniem do kierowania raportu ZO i odpowiadania na raporty arkusza do preferowanego miejsca docelowego.

ZO można tworzyć dla zamówienia zakupu, który ma typ **Zamówienie zakupu** lub **Umowa zakupu**.

Jeśli ZO ma typ **Zamówienie zakupu** ma miejsce następująca sytuacja:

- Podczas tworzenia wierszy ZO generowane są transakcje magazynowe, które mają stan przyjęcia **Przyjęcie oferty**.
- Po zaakceptowaniu oferty generowane jest zamówienie zakupu.

Jeśli ZO ma typ **Umowa zakupu** ma miejsce następująca sytuacja:

- ZO jest używane dla umowy zakupu do zakupu ilości lub wartości produktu w określonym czasie. Należy wybrać zakres dat, którego dotyczy umowa zakupu i nazwisko osoby, która zarządza umową.
- Po zaakceptowaniu oferty generowana jest umowa zakupu.

Jeśli ZO jest generowane na podstawie zapotrzebowania na zakup, typ **Zapotrzebowanie na zakup** jest przypisywany automatycznie. Nie można ręcznie utworzyć ZO typu **Zapotrzebowanie na zakup**.

Można utworzyć ZO z zapotrzebowania na zakup tylko wtedy, gdy zapotrzebowanie na zakup ma stan **W trakcie przeglądu**, a następne zadania przepływu pracy jest przypisane do użytkownika. Wiersze zapotrzebowania na zakup są automatycznie aktualizowane, gdy użytkownik akceptuje wiersze z odpowiedzi na ZO (ofert) otrzymywanych od dostawców. W trakcie przetwarzania zapytania ofertowego nie można sporządzić, odrzucić, zatwierdzić czy wykonywać żadnych innych działań dotyczących zapotrzebowania na zakup.

Po utworzeniu ZO można wybrać typ zdobywania zamówień. Typ zdobywania zamówień określa zestaw kryteriów punktowania służący do odpowiedzi na ZO.

Kwestionariusz można dodać do sprawy ZO. Będzie on widoczny we wszystkich odpowiedziach po wysłaniu ZO.

Istnieją trzy sposoby wyboru dostawców dodawanych do sprawy ZO:

- Dodawanie dostawców po kolei.
- Wyszukiwanie wszystkich dostawców spełniających określone kryteria.
- Automatyczne dodawanie wszystkich dostawców, którzy zostali zatwierdzeni dla kategorii zaopatrzenia używanych w wierszach ZO.

Gdy sprawa ZO jest gotowa, wybierz opcję **Wyślij**. Akcja Wyślij tworzy nowe arkusze i raporty, które będzie można drukować, archiwizować i wysyłać zgodnie z ustawieniami zarządzania drukowaniem.

Jeśli ustawiono opcję **Użyj dostawcy w celu ponownego obliczenia cen** i **Użyj informacji o towarze specyficznym dostawcy** na **Tak** na stronie **Wysyłanie zapytania ofertowego** po wysłaniu ZO do dostawców, niektóre informacje właściwe dla dostawcy są wprowadzane automatycznie. Można zmienić te informacje na stronie **Odpowiedź na zapytanie ofertowe**.

W poniższej tabeli przedstawiono, jak zmienia się stan ZO przy tworzeniu ZO i wysyłaniu go do dostawców.

| Akcja                             | Najniższy stan nagłówka ZO | Najwyższy stan nagłówka ZO                        | Najniższy stan wiersza ZO | Najwyższy stan wiersza ZO |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Utwórz nagłówek i wiersz ZO.    | Utworzone                  | Utworzone                                          | Utworzone                | Utworzone |
| Wysyłanie ZO do określonego dostawcy. | Wysłano                     | Wysłano                                             | Wysłano                   | Wysłano |
| Dodwanie nowego dostawcy.                | Utworzone                  | Wysłane (ZO zostało wysłane do tylko jednego dostawcy.) | Utworzone                | Wysłano |
| Wysyłanie ZO do drugiego dostawcy. | Wysłano                     | Wysłano                                             | Wysłano                   | Wysłano |

> [!NOTE]
> Można dodać kolejnych dostawców do ZO w dowolnym momencie, a najniższe i najwyższe stany zostaną zaktualizowane, aby odzwierciedlić nowych dostawców, którzy zostali dodani. Na przykład, jeśli otrzymano oferty od wszystkich dostawców, a co najmniej jeden wiersz oferty zaakceptowano, najniższy stan w nagłówku ZO to **Odrzucono**, a najwyższy stan to **Zaakceptowany**. Po dodaniu nowego dostawcy, najniższy stan w dowolnym wierszu zostanie zmieniony na **Utworzono**. Dlatego najniższy stan w nagłówku ZO jest aktualizowany na **Utworzono**, ale najwyższy stan pozostaje ustawiony na **Zaakceptowane**.

## <a name="amending-an-rfq"></a>Zmienianie ZO

Czasami trzeba zmienić ZO, które zostało już wysłane. Zmiana ZO może być wymagana na przykład, gdy zmienią się terminy dostawy lub trzeba dodać produkty albo zmienić ilości produktów. Proces zmiany można skonfigurować w taki sposób, by był bardziej lub mniej restrykcyjny.

Jeżeli skonfigurowano proces zmiany tak, aby był bardziej restrykcyjny, przed zmodyfikowaniem pól w sprawie ZO, które zostało już wysłane należy wybrać opcję **Utwórz** w sprawie ZO, aby rozpocząć zmianę. Po ukończeniu zmian należy wybrać opcję **Finalizuj**. Następnie redaguje się powiadomienia wysyłane w wiadomości e-mail do dostawców i informujące ich o wprowadzonych zmianach. Zaktualizowany raport ZO z informacją o zmianie jest automatycznie dołączany do wiadomości e-mail.

W przypadku skonfigurowania mniej restrykcyjnej metody wprowadzania zmian nie trzeba wybierać opcji **Utwórz** przed zmodyfikowaniem pól w sprawie ZO, które zostało już wysłane. Trzeba jednak ręczne wpisać informację o zmianie na ZO i wysłać tę sprawę ponownie. Należy pamiętać, że tej metody można użyć tylko wtedy, gdy żadne odpowiedzi (oferty) nie były edytowane. Jeżeli wprowadzono odpowiedź i jest ona w stanie **Odebrana** przycisk **Wyślij** jest niedostępny. W takim przypadku należy wybrać opcję **Utwórz**, a następnie **Finalizuj**, podobnie jak w bardziej restrykcyjnym procesie. Odpowiedź jest następnie resetowana, aby uwzględniała zmiany w sprawie ZO. 

Jeżeli dostawcy korzystają z interfejsu portalu współpracy dostawcami do wprowadzania ofert, należy zawsze użyć procesu zmiany do powiadomienia dostawców o zmianach w sprawie ZO. To wymagania pozwala zapobiec sytuacji, w której dostawcy składają oferty dotyczące nieaktualnej sprawy ZO, gdy ich oferta jest w toku. Aby uzyskać więcej informacji o portalu współpracy z dostawcami, zobacz [Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami](vendor-collaboration-work-external-vendors.md). 

Jeżeli chcesz zastąpić dodatkowych dostawców do oferty i nie wprowadzono zmian w sprawie RFQ case, możesz użyć przycisku **Wyślij**. Dodani dostawcy będą widoczni na stronie **Wyślij** i otrzymają zaproszenie w wiadomości e-mail.

## <a name="receiving-and-registering-rfq-replies"></a>Odbieranie i rejestrowanie odpowiedzi na ZO

Podczas wysyłania ZO, automatycznie jest generowany arkusz odpowiedzi. Po otrzymaniu odpowiedzi (oferty) na ZO w arkuszu odpowiedzi na ZO specyficzne dla dostawcy trzeba wprowadzić informacje od każdego dostawcy. Po dodaniu kryteriów punktowania można przydzielić odpowiedziom punkty. Następnie porównuje się oferty dostawców i ocenia je według takich kryteriów oceniania, jak najlepsza cena całkowita lub najlepszy całkowity czas dostawy.

Jeśli do sprawy ZO dołączony jest kwestionariusz, trzeba ręcznie wpisać odpowiedzi na pytania w arkuszu odpowiedzi.

Można także wprowadzić wiersze alternatywne, jeżeli sprawa ZO je dopuszcza. Na skróconej karcie **Wiersze oferty zakupu** wybierz opcję **Dodaj wiersz**. Następnie wprowadź informacje o produkcie, takie jak ilość, cena i rabaty, kod towaru lub kategoria zaopatrzenia.

Jeśli została wprowadzona odpowiedź, ale wymagana jest nowa oferty od dostawcy, można ponownie wysłać ZO. Zostanie wygenerowany nowy arkusz i raport, za pomocą których można poprosić dostawcę o wprowadzenie zmian.

Podsumowanie wszystkich ZO i ich stanów odpowiedzi jest widoczne na stronie **Kolejne czynności dla zapytania ofertowego**.

W poniższej tabeli przedstawiono, jak zmienia się stan ZO podczas odbierania ofert i rejestrowania informacji w arkuszu odpowiedzi na ZO.

| Akcja                                         | Najniższy stan oferty | Najwyższy stan oferty | Najniższy stan nagłówka ZO | Najwyższy stan nagłówka ZO | Najniższy stan wiersza ZO | Najwyższy stan wiersza ZO |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Rejestrowanie oferty jednego dostawcy i zapisywanie jej.        | Wysłany              | Odebrane           | Wysłany                     | Odebrane                  | Wysłany                   | Odebrane |
| Rejestrowanie oferty drugiego dostawcy i zapisywanie jej. | Odebrane          | Odebrane           | Odebrane                 | Odebrane                  | Odebrane               | Otrzymane |

> [!NOTE]
> Jeśli zwrócisz ofertę dostawcy w celu dodatkowych negocjacji, najniższy i najwyższy stan nie zmienia się i jest następujący: **Otrzymano**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Akceptowanie i odrzucenia ofert i przenoszenie zaakceptowanych ofert do dokumentów przesyłanych od dostawcy do odbiorcy

Po znalezieniu najlepszej oferty, takiej jak oferta, która z najlepszą ceną całkowitą, należy zaakceptować ofertę. Można zaakceptować niektóre wiersze oferty i odrzucić inne. Można również zaakceptować wiersze pochodzące od różnych dostawców. Należy pamiętać, że w przypadku zaakceptowania niektórych wierszy pojawi się monit o odrzuceniu wszystkich pozostałych. Aby zaakceptować te pozostałe wiersze, należy wybrać opcję **Anuluj** po pojawieniu się monitu. Stan odpowiedzi ZO dla każdego dostawcy, od którego akceptujesz oferty lub wiersze zostanie zaktualizowany na **Zaakceptowano**. 

Po zaakceptowaniu oferty lub określonych wierszy oferty zamówienie zakupu lub umowa zakupu są generowane automatycznie. Następnie można odrzucić oferty od wszystkich innych dostawców.

Po uzyskaniu odpowiedzi można dodać kod przyczyny wyjaśniającej, dlaczego oferta została przyjęta lub odrzucona.

Po zaakceptowaniu odpowiedzi na ZO typu **Zapotrzebowanie na zakup**, wiersze takiej odpowiedzi uaktualnią wiersze zapotrzebowania zakupu następującymi informacjami:

- Cena jednostkowa
- Procent rabatu
- Kwota rabatu
- Opłaty od zakupu
- Opłaty za wierszy
- Dostawca
- numer zewnętrzny,
- Zewnętrzny opis

W poniższej tabeli przedstawiono, jak zmienia się stan ZO w przypadku akceptowania lub odrzucania ofert od dostawców.

| Akcja                      | Najniższy stan oferty | Najwyższy stan oferty | Najniższy stan nagłówka ZO | Najwyższy stan nagłówka ZO | Najniższy stan wiersza ZO | Najwyższy stan wiersza ZO |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Zaakceptowanie jednej z ofert.     | Odebrane          | Zaakceptowana           | Odebrane                 | Zaakceptowana                  | Odebrane               | Zaakceptowana |
| Odrzucenie wszystkich innych ofert.  | Odrzucona          | Zaakceptowana           | Odrzucona                 | Zaakceptowana                  | Odrzucona               | Zaakceptowany |

