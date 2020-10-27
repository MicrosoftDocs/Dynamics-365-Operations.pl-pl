---
title: Omówienie zapytań ofertowych (ZO)
description: W tym temacie opisano zapytania ofertowe (ZO). Organizacje wystawiają zapytania ofertowe (ZO), kiedy chcą uzyskać od kilku dostawców konkurencyjne oferty na produkty i usługi, które muszą kupić.
author: mkirknel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage, BOMExpandPurchRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aec0ce03d438f8153b9555a079b6fd97f6a95a5
ms.sourcegitcommit: ae04c7cb48f7ecafe71bbe77a0f97715e6290991
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973507"
---
# <a name="requests-for-quotation-rfqs-overview"></a>Omówienie zapytań ofertowych (ZO)

[!include [banner](../includes/banner.md)]

W tym temacie opisano zapytania ofertowe (ZO). Organizacje wystawiają zapytania ofertowe (ZO), kiedy chcą uzyskać od kilku dostawców konkurencyjne oferty na produkty i usługi, które muszą kupić. W ZO dostawcy są proszeni o podanie cen i terminów dostaw dla ilości towarów określonych przez użytkownika.
Można również poprosić dostawców, aby określili, czy są jakieś dodatkowe opłaty, takie jak koszty wysyłki, albo zniżki za duże zamówienia lub szybką zapłatę faktury.

Proces ZO składa się z następujących zadań:

1. Utworzenie i wysyłanie ZO do jednego lub większej liczby dostawców.
1. Otrzymywanie i rejestrowanie ofert (odpowiedzi na ZO).
1. Przenoszenie zaakceptowanych ofert do zamówienia zakupu, umowy zakupu lub zapotrzebowania na zakup.

Na poniższej ilustracji przedstawiono przegląd procesu ZO.

[![Proces RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Sprawy ZO można tworzyć z zamówień planowanych lub zapotrzebowań na zakup albo wprowadzać je ręcznie. Sprawa ZO to podstawowy dokument używany do wysyłania ZO do każdego dostawcy.

Po przygotowaniu sprawy ZO i dodaniu dostawców wybierz opcję **Wyślij** (**Wysyłanie i publikowanie** w przypadku podmiotów z sektora publicznego) w sprawie ZO. Dla każdego dostawcy, do którego wysłano ZO generowany jest arkusz ZO. Można skonfigurować opcje drukowania dla akcji wysyłania, aby wydrukować raport dla każdego dostawcy w celu archiwizowania, lub wysłać raporty na adresy e-mail dostawców. Ponadto arkusz ZO dla każdego dostawcy może służyć do generowania raportu, który można wysłać lub później ponownie wysłać do dostawcy. Można również skonfigurować akcję wysłania, aby wygenerować arkusz odpowiedzi, który mogą wypełniać dostawcy.

W tym temacie opisano proces obsługi ZO, gdy nie jest używana współpraca z dostawcą. Jeśli system jest skonfigurowany do współpracy z dostawcami, dostawcy mogą wprowadzić oferty bezpośrednio w rozwiązaniu Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Współpraca z odbiorcami przy użyciu modułu Współpraca z dostawcami](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) i [Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami](vendor-collaboration-work-external-vendors.md).

Jeżeli po wysłaniu wymagana jest zmiana ZO, po zakończeniu można ponownie wysłać ZO do dostawców, korzystając z dwóch akcji zmian: Utwórz i Finalizuj.

Po otrzymaniu ofert w wiadomości e-mail można je obsługiwać na stronie **Zapytania ofertowe**.

Jeśli w przypadku danego dostawcy wymagana jest druga iteracja odpowiedzi, wybierz opcję **Zwrot** na stronie **Zapytanie ofertowe**. Akcja zwrotu tworzy nowy arkusz i raport, który będzie można wydrukować, archiwizować i wysyłać zgodnie z ustawieniami drukowania.

Po dodaniu do sprawy ZO kryteriów punktowania ZO będzie miało panel punktowania, w którym można wprowadzać oceny. Całkowity wynik będzie widoczny w ZO oraz po porównaniu odpowiedzi na stronie **Porównaj odpowiedzi**. Na stronie **Porównaj odpowiedzi** można także porównać inne dane odpowiedzi, takie jak cena wiersza, data dostawy i cena łączna.

Po wybraniu oferty lub określonych wierszy z oferty można zaakceptować wszystkie lub niektóre wiersze, a odrzucić pozostałe. Arkusze przyjęcia, odrzucenia i odpowiednie raporty zostaną wygenerowane oraz wydrukowane, zarchiwizowane i wysłane zgodnie z ustawieniami drukowania. Po zaakceptowaniu oferty lub określonych wierszy oferty w zależności od typu zakupu ZO tworzona jest umowa zakupu lub zamówienie zakupu lub aktualizowane jest zapotrzebowanie na zakup. Można utworzyć umowę handlową, której można następnie użyć w odpowiedziach, bez względu na to, czy je odrzucasz czy akceptujesz.

Sprawa ZO ma dwa stany: najniższy i najwyższy. Stan można sprawdzić na stronie listy **Wszystkie zapytania ofertowe**. Najniższy stan jest najmniej zaawansowanym etapem wiersza sprawy ZO, a najwyższy stan jest najbardziej zaawansowanym etapem wiersza w sprawie ZO. Załóżmy na przykład, że sprawa ZO z trzema wierszami jest wysyłana do dwóch dostawców, więc istnieją dwa ZO, każde z trzema wierszami. Wszystkie wiersze mają status **Wysłane**. Następnie jest wprowadzana oferta od jednego z dostawców, a wiersze ZO uzyskują stan **Otrzymane**. Oznacza to, że z trzech wierszy w sprawie ZO wszystkie mają status **Wysłane** dla jednego ZO i **Otrzymane** dla drugiego ZO. Najniższy stan będzie miał zatem wartość **Wysłane**, a najwyższy **Otrzymane**.

Te stany zostaną opisane bardziej szczegółowo w dalszej części tego tematu.

## <a name="setting-up-rfq-functionality"></a>Konfigurowanie funkcji ZO

Aby można było tworzyć sprawy ZO, należy skonfigurować informacje ZO na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu sprawy ZO można określić wartości domyślne, które są kopiowane do ZO. Można określić następujące wartości domyślne:

- Typ zakupu nowych ZO: **Zamówienia zakupu** lub **Umowy zakupu**
- Przesunięcie daty i godziny ważności od dnia utworzenia sprawy ZO.
- Typ zdobywania zamówień, który może domyślnie podstawiać określoną metodę punktowania do sprawy ZO.
- Informacje o dostawie i warunki płatności.

Można zastąpić te wartości dla określonej sprawy ZO.

Należy także skonfigurować proces poprawki. W ramach tej konfiguracji można włączyć pole blokowania. Jeśli blokowanie pól jest włączone, pracownik działu zaopatrzenia, który chce zmienić ZO, musi najpierw wybrać opcję **Utwórz** w sekcji **Poprawki** na karcie **Oferta** sprawy ZO. Następnie po zaktualizowaniu sprawy ZO o poprawkę pracownik działu zaopatrzenia musi ukończyć proces, wybierając opcję **Finalizuj**. Akcja Finalizuj generuje wiadomość e-mail powiadamiającą dostawcę o poprawionym ZO.

Na stronie **Parametry modułu Zaopatrzenie i sourcing** można wybrać szablon do użycia dla powiadomienia w wiadomości e-wysyłanego do dostawców. Po utworzeniu szablonu w oknie **Szablony wiadomości e-mail** może on zawierać następujące tokeny wymiany:

- %RFQ case%
- %Przyczyna zwrotu oferty%
- %Przyczyna sporządzenia poprawki%
- %Poprawka przygotowana przez%
- %Firma%
- %RFQ case name%
- %Expiry Date Time%
- %Date%

Tokeny %Przyczyna zwrotu oferty% i %Przyczyna sporządzenia poprawki% zastępuje tekst, który pracownik działu zakupów może wpisać po zakończeniu poprawki w **kreatorze poprawek**. Wartości tokenów %poprawki przygotowane przez% i %firma% są automatycznie pobierane z ZO. Token %Date% jest zastępowany przez bieżącą datę.

Jeśli chcesz anulować ZO po jego wysłaniu, można to zrobić z poziomu sprawy ZO. W przypadku anulowania należy użyć szablonu wiadomości e-mail, aby wysłać powiadomienie o anulowaniu do osób kontaktowych dostawcy. Szablon należy wybrać na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po utworzeniu szablon może zawierać następujące tokeny wymiany:

- %Reason for cancellation%
- %RFQ case%
- %RFQ cancelled by%
- %Firma%
- %RFQ case name%
- %Date%

Token %Reason for cancellation% jest zastępowany przez tekst, który specjalista ds. zaopatrzenia może wprowadzić w kreatorze **Anulowanie**. Token %Date% jest zastępowany przez bieżącą datę.

Jeśli chcesz użyć kodów przyczyn w ofercie, aby wskazać, dlaczego oferta została zaakceptowana lub odrzucona, musisz ustawić te kody na stronie **Przyczyny dotyczące dostawcy**.

Na stronie **Ustawienia formularza** w module Zaopatrzenie and sourcing, można skonfigurować wygląd drukowanych lub przechowywanych dokumentów ZO.

> [!NOTE]
> W przypadku konfiguracji sektora publicznego należy użyć procesu zmiany w celu zmiany ZO, które zostało już wysłane. Po wysłaniu ZO pola są blokowane.
Dlatego w celu wprowadzenia zmian w ZO należy wybrać opcję **Utwórz**, aby rozpocząć proces zmiany zgodnie z wcześniejszym opisem. Blokowanie jest kontrolowane za pomocą opcji **Zablokuj ZO, gdy zostaną wysłane** na stronie **Parametry modułu Zaopatrzenie i sourcing**. Domyślnie ten parametr ma ustawioną wartość **Tak** i w konfiguracji dla sektora publicznego jest to ustawienie domyślne, którego nie można zmienić. Dlatego, mimo że proces zmiany można obsłużyć ręcznie w konfiguracji sektora niepublicznego, należy go użyć do konfiguracji sektora publicznego.

Gdy tworzysz sprawę ZO typu Zamówienie zakupu i dodajesz pozycję magazynową do ZO, zostaje wygenerowana transakcja magazynowa, która ma stan przyjęcia **Otrzymanie oferty**. Tylko wiersze sprawy ZO z tym stanem są uwzględniane podczas korzystania z planu głównego do obliczania dostaw. Aby uwzględniać wiersze sprawy ZO jako oczekiwane przyjęcia planu głównego, należy skonfigurować to zachowanie w ustawieniach planowania głównego.

Jako menedżer lub agent ds. zakupów możesz tworzyć i obsługiwać typy zdobywania zamówień tak, aby spełniały wymogi zamówień dla danej organizacji. Każdy typ zdobywania zamówień można powiązać z metodą punktowania. Metody punktowania zawierają szereg kryteriów, których można używać podczas oceny ofert. Należy skonfigurować typy zdobywania zamówień, metody punktowania oraz kryteria określania wyników na stronach **Typ zdobywania zamówień** i **Metoda punktowa**.

## <a name="choose-default-fields-to-include-in-vendor-rfq-reply-forms"></a><a name="default-reply-fields"></a>Wybierz pola domyślne, które mają być uwzględnione w formularzach odpowiedzi na ZO dostawcy

Możesz określić typy informacji, które chcesz otrzymać od dostawców w odpowiedziach (złożonych ofertach) na zapytanie ofertowe (ZO). Pola, które należy oznaczyć jako domyślne, są zawarte w formularzu online dostarczonym do współpracy z dostawcami. Aby określić ustawienia:

1. Jeśli nie zostało to jeszcze zrobione, Skorzystaj ze strony [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcje *Wybierz pola ZO, które mają być uwzględnione w formularzach odpowiedzi na ZO dostawcy*.
1. Przejdź do **Zaopatrzenie i sourcing > Ustawienia > Parametry modułu Zaopatrzenie i sourcing**.
1. Otwórz kartę **Zapytanie ofertowe**.
1. Wybierz łącze pól odpowiedzi **Domyślne zapytania ofertowe** w obszarze **Ustaw wartości domyślne dla zapytań ofertowych**.
1. Zostanie otwarte okno dialogowe **Domyślne pola odpowiedzi na zapytanie ofertowe**.
1. **Pola ZO uwzględnione w formularzach odpowiedzi na ZO dostawców** zawierają suwak dla każdego pola, które jest dostępne do użytku w formularzach odpowiedzi na ZO. Pola ustawione na wartość *Tak* w tej sekcji zostaną uwzględnione (wraz z ich wartościami) w formularzach odpowiedzi na ZO. Ustaw suwak na wartość *Nie* dla każdego pola, w którym dostawcy nie będą mogli wyświetlać danych podczas przeglądania ofert. Umożliwia to wprowadzenie oszacowanych lub oczekiwanych wartości podczas wprowadzania ZO do celów wewnętrznych, bez konieczności wyświetlania przez dostawcę tego, co zostało wprowadzone.

W razie potrzeby można zastąpić te ustawienia dla poszczególnych spraw ZO.

## <a name="creating-and-sending-an-rfq"></a>Tworzenie i wysyłanie ZO

Utwórz sprawę ZO, wybierz dostawców, od których chcesz uzyskać oferty dla sprawy ZO, a następnie wyślij ZO do dostawców. Można użyć ustawień drukowania do kierowania raportu ZO i raportów arkuszy odpowiedzi do preferowanego miejsca docelowego.

Można ręcznie utworzyć sprawę ZO o typie zakupu **Zamówienie zakupu** lub **Umowa zakupu**.

Jeśli sprawa ZO jest typu **Zamówienie zakupu**, występuje następujące zachowanie różniące się od innych typów spraw ZO:

- Podczas tworzenia wierszy sprawy ZO generowane są transakcje magazynowe, które mają stan przyjęcia **Przyjęcie oferty**.
- Po zaakceptowaniu oferty generowane jest zamówienie zakupu.

Jeśli ZO jest typu **Umowa zakupu**, występuje następujące zachowanie różniące się od innych spraw ZO:

- Sprawa ZO jest używana dla umowy zakupu w celu zakupu określonej ilości lub wartości produktu w pewnym czasie. Należy wybrać zakres dat, którego dotyczy umowa zakupu i nazwisko osoby, która zarządza umową.
- Po zaakceptowaniu oferty generowana jest umowa zakupu.

Jeśli sprawa ZO jest generowana na podstawie zapotrzebowania na zakup, typ **Zapotrzebowanie na zakup** jest przypisywany automatycznie. Nie można ręcznie utworzyć sprawy ZO typu **Zapotrzebowanie na zakup**.

Można utworzyć sprawę ZO z zapotrzebowania na zakup tylko wtedy, gdy zapotrzebowanie na zakup ma stan **W trakcie przeglądu**, a następne zadanie przepływu pracy jest przypisane do użytkownika. Wiersze zapotrzebowania na zakup są automatycznie aktualizowane, gdy użytkownik akceptuje wiersze z ofert (odpowiedzi na ZO) otrzymywanych od dostawców. Nie można sfinalizować, odrzucić, zatwierdzić ani wykonywać innych operacji na zapotrzebowaniu na zakup, dopóki wiersz zapotrzebowania nie zostanie zaktualizowany o zaakceptowany wiersz ZO lub sprawa ZO nie zostanie anulowana.

Po utworzeniu sprawy ZO można wybrać typ zdobywania zamówień. Typ zdobywania zamówień określa zestaw kryteriów punktowania służący do punktowania odpowiedzi na ZO w sprawie ZO.

Kwestionariusz można dodać do sprawy ZO. Będzie on widoczny we wszystkich odpowiedziach na ZO po wysłaniu ZO. Wypełnienie kwestionariusza jest zadaniem wymaganym, zanim będzie można przesłać ofertę.

Chociaż są dostępne wartości domyślne, w razie potrzeby można zmienić ustawienia **pól ZO zawartych w ustawieniach formularzy odpowiedzi na ZP dostawców** dla poszczególnych spraw ZO. W tym celu utwórz lub otwórz sprawę ZO. Następnie w okienku akcji kartę **Oferta**, a następnie w sekcji **Odpowiedzi** wybierz opcję **Ustaw wartości domyślne odpowiedzi na ZO**. Zostanie otwarte okno dialogowe **Domyślne pola odpowiedzi na zapytanie ofertowe**, które działa tak samo, jak podczas wyboru ustawień domyślnych dla formularzy odpowiedzi na ZO, z wyjątkiem tego, że zmian wprowadzone tutaj mają wpływ tylko na bieżącą sprawę ZO. Aby uzyskać szczegółowe informacje dotyczące włączania tej funkcji i sposobu jej działania, zobacz temat [Wybierz pola domyślne, które mają być uwzględnione w formularzach odpowiedzi na ZO dostawców](#default-reply-fields).

Istnieją trzy sposoby wyboru dostawców dodawanych do sprawy ZO:

- Dodawanie dostawców po kolei.
- Wyszukiwanie wszystkich dostawców spełniających określone kryteria.
- Automatyczne dodawanie wszystkich dostawców, którzy zostali zatwierdzeni dla kategorii zaopatrzenia używanych w wierszach sprawy ZO.

Gdy sprawa ZO jest gotowa, wybierz opcję **Wyślij**. Akcja Wyślij tworzy nowe arkusze i raporty, które będzie można drukować, archiwizować i wysyłać zgodnie z ustawieniami drukowania.

Jeśli podczas wysyłania ZO do dostawcy ustawiono opcję **Użyj dostawcy w celu ponownego obliczenia cen** i **Użyj informacji o towarze specyficznym dostawcy** na **Tak** na stronie **Wysyłanie zapytania ofertowego**, niektóre informacje właściwe dla dostawcy są wprowadzane automatycznie w ZO dla tego dostawcy.

## <a name="amending-an-rfq-case"></a>Wprowadzanie poprawek w sprawie ZO

Czasami trzeba zmienić treść sprawy ZO, która została już wysłana. Zmiana w sprawie ZO może być wymagana na przykład wtedy, gdy zmienią się terminy dostawy lub trzeba dodać produkty albo zmienić ilości produktów. Proces zmiany można skonfigurować w taki sposób, by był bardziej lub mniej restrykcyjny.

Jeżeli skonfigurowano proces zmiany tak, aby był bardziej restrykcyjny, przed zmodyfikowaniem pól w sprawie ZO, które zostało już wysłane należy wybrać opcję **Utwórz** w sprawie ZO, aby rozpocząć zmianę. Po ukończeniu zmian należy wybrać opcję **Finalizuj**. Następnie redaguje się powiadomienia wysyłane w wiadomości e-mail do dostawców i informujące ich o wprowadzonych zmianach. Zaktualizowany raport ZO z informacją o zmianie jest automatycznie dołączany do wiadomości e-mail.

W przypadku skonfigurowania mniej restrykcyjnej metody wprowadzania zmian nie trzeba wybierać opcji **Utwórz** przed zmodyfikowaniem pól w sprawie ZO, które zostało już wysłane. Trzeba jednak ręczne wpisać informację o zmianie na ZO i wysłać tę sprawę ponownie. Należy pamiętać, że tej metody można użyć tylko wtedy, gdy żadne odpowiedzi (oferty) nie były edytowane. Jeżeli wprowadzono odpowiedź i jest ona w stanie **Odebrana** przycisk **Wyślij** jest niedostępny. W takim przypadku należy wybrać opcję **Utwórz**, a następnie **Finalizuj**, podobnie jak w bardziej restrykcyjnym procesie. Odpowiedź jest następnie resetowana, aby uwzględniała zmiany w sprawie ZO.

Jeżeli dostawcy korzystają z interfejsu portalu współpracy dostawcami do wprowadzania ofert, należy zawsze użyć procesu zmiany do powiadomienia dostawców o zmianach w sprawie ZO. Ten proces pozwala zapobiec sytuacji, w której dostawcy składają oferty dotyczące nieaktualnej sprawy ZO, gdy ich oferta jest w toku. Aby uzyskać więcej informacji o portalu współpracy z dostawcami, zobacz [Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Jeżeli chcesz zastąpić dodatkowych dostawców do oferty i nie wprowadzono zmian w sprawie RFQ case, możesz użyć przycisku **Wyślij**. Dodani dostawcy będą widoczni na stronie **Wyślij** i otrzymają zaproszenie w wiadomości e-mail.

## <a name="receiving-and-registering-rfq-replies"></a>Odbieranie i rejestrowanie odpowiedzi na ZO

Podczas wysyłania ZO, automatycznie jest generowany arkusz odpowiedzi. Oferty otrzymywane w odpowiedzi na ZO należy na bieżąco wprowadzać na stronie **Zapytanie ofertowe**, klikając przycisk akcji **Edytuj odpowiedź na ZO**. Pozwoli to wprowadzać dane ofert w dedykowanym formularzu ofert. Początkowo pole **Postęp odpowiedzi** ma wartość **Nie rozpoczęto**. Po kliknięciu przycisku **Edytuj odpowiedź na ZO** stan postępu ma wartość **Nabywca aktualizuje** aż do przesłania oferty. Po wprowadzeniu danych oferty kliknij przycisk **Prześlij**. Pole stanu Postęp odpowiedzi zmieni wartość na **Przesłana przez nabywcę**. Podobnie po włączeniu obszaru roboczego współpracy z dostawcami pole **Postęp odpowiedzi** będzie aktualizowane wraz z kolejnymi interakcjami dostawcy z ofertą. Stan zmienia się następnie z **Dostawca aktualizuje** na **Przesłana przez dostawcę**. Po przesłaniu oferty jest tworzony arkusz ze stanem **Otrzymane**. Odpowiedź (oferta) musi zostać przesłana, aby została zarejestrowana jako otrzymana. Dopiero wtedy można ją przetwarzać dalej jako zaakceptowaną lub odrzuconą.

Jeśli zachodzi konieczność aktualizacji oferty, trzeba przejść przez ten sam proces, co wyżej, i przesłać ją ponownie.

Należy zauważyć, że edycja formularza **Zapytanie ofertowe** jest dozwolona tylko w zakresie informacji dotyczących przetwarzania oferty, a nie wprowadzania oferty. Aby wprowadzić lub zmodyfikować ofertę, kliknij przycisk **Edytuj odpowiedź na ZO**.

Jeżeli sprawa ZO pozwala na wiersze alternatywne, podczas wprowadzenia danych oferty można dodać wiersze alternatywne dla wierszy, w których określono tylko kategorię zaopatrzenia, bez towaru z katalogu. Aby dodać wiersze alternatywne, kliknij przycisk **Dodaj alternatywę**.

Jeśli została wprowadzona odpowiedź, ale wymagana jest nowa oferta od dostawcy, można zwrócić ZO. Zostaną wygenerowane nowy arkusz i raport, które można wysłać do dostawcy.

Podsumowanie wszystkich ZO i ich stanów **Wysłane, Otrzymane, Zaakceptowane, Odrzucone, Anulowane, Niezaakceptowane** jest widoczne na stronie **Kolejne czynności dla zapytania ofertowego**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Akceptowanie i odrzucenia ofert i przenoszenie zaakceptowanych ofert do dokumentów przesyłanych od dostawcy do odbiorcy

Po znalezieniu najlepszej oferty, takiej jak oferta, która z najlepszą ceną całkowitą, należy zaakceptować ofertę. Można zaakceptować niektóre wiersze oferty i odrzucić inne.
Można również zaakceptować wiersze pochodzące od różnych dostawców. Należy pamiętać, że w przypadku zaakceptowania niektórych wierszy pojawi się monit o odrzuceniu wszystkich pozostałych. Aby zaakceptować te pozostałe wiersze, należy wybrać opcję **Anuluj** po pojawieniu się monitu. Stan odpowiedzi ZO dla każdego dostawcy, od którego akceptujesz oferty lub wiersze zostanie zaktualizowany na **Zaakceptowano**.

Jeśli podczas przygotowywania zamówienia zakupu lub umowy zakupu trzeba dodać kolejny wiersz do ZO, można to zrobić przez kliknięcie przycisku **Dodaj wiersz** w siatce wierszy na stronie **Zapytanie ofertowe**. Ten wiersz można wyświetlać i edytować tylko na stronie **Zapytanie ofertowe**. Będzie on widoczny na stronie oferty po zaakceptowaniu.

Po zaakceptowaniu oferty albo jednego lub więcej wierszy oferty zostanie automatycznie wygenerowane zamówienie zakupu lub umowa zakupu. Następnie można odrzucić oferty od wszystkich innych dostawców.

Po uzyskaniu odpowiedzi można dodać kod przyczyny wyjaśniającej, dlaczego oferta została przyjęta lub odrzucona.

Po zaakceptowaniu oferty typu **Zapotrzebowanie na zakup** wiersze zapotrzebowania na zakup zostaną zaktualizowane o następujące informacje, które odzwierciedlają dane zaakceptowanej oferty:

- Cena jednostkowa
- Procent rabatu
- Kwota rabatu
- Opłaty od zakupu
- Opłaty za wierszy
- Dostawca
- numer zewnętrzny,
- Zewnętrzny opis

W poniższej tabeli przedstawiono, jak zmienia się stan ZO w przypadku akceptowania lub odrzucania ofert od dostawców.

## <a name="statuses--highest-and-lowest"></a>Stany — najniższy i najwyższy

W oknie sprawy ZO na karcie Dostawca widać wiersze z najwyższym i najniższym stanem dla określonego dostawcy. Po dodaniu dostawcy, jeżeli nie wysłano jeszcze żadnych wierszy, zarówno najniższy, jak i najwyższy stan to <strong>Utworzone</strong>. Po wysłaniu ZO do dostawcy ze wszystkimi wierszami stan tych dwóch wierszy zmieni się na <strong>Wysłane</strong>. Jeśli niektóre wiersze w ofercie od dostawcy są zaakceptowane, a inne są odrzucone, odrzucone wiersze otrzymają najniższy stan, którym jest <strong>Odrzucone</strong>, a wiersze zaakceptowane otrzymają najwyższy stan, którym jest <strong>Zaakceptowane</strong>.

W wierszach sprawy ZO widać najwyższy i najniższy stan każdego wiersza u wszystkich dostawców. Jeśli wiersz został wysłany do wszystkich dostawców w sprawie ZO, a jeszcze nikt nie odpowiedział, najniższy i najwyższy stan mają wartość **Wysłane**. Gdy co najmniej jeden dostawca odpowie, najwyższy stan zmienia się na **Otrzymane**. Po dodaniu nowego dostawcy do sprawy najniższy stan zmienia się na **Utworzone**

Najwyższy i najniższy stan w sprawie ZO są agregacją stanu z kart \<Dostawca i Wiersze.

Stany są uszeregowane w następującym porządku od najniższego do najwyższego: Utworzone, Wysłane, Otrzymane, Odrzucone, Zaakceptowane, Niezaakceptowane i Anulowane.

W poniższej tabeli przedstawiono, jak zmienia się stan sprawy ZO przy tworzeniu sprawy ZO z wierszami, a następnie wysyłaniu jej do dostawców.

| **Akcja**                                | **Najniższy stan sprawy ZO** | **Najwyższy stan sprawy ZO** | **Najniższy stan wiersza sprawy ZO** | **Najwyższy stan wiersza sprawy ZO** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Tworzenie nagłówka i wiersza sprawy ZO.      | Utworzono                    | Utworzono                     | Utworzono                         | Utworzono                          |
| Wysyłanie ZO do wszystkich dostawców w sprawie ZO. | Wysłany                       | Wysłany                        | Wysłany                            | Wysłany                             |
| Dodwanie nowego dostawcy.                       | Utworzono                    | Wysłany                        | Utworzono                         | Wysłany                             |
| Wysyłanie ZO do drugiego dostawcy.        | Wysłany                       | Wysłany                        | Wysłany                            | Wysłany                             |

Wszystkie wiersze w ZO związane ze sprawą ZO będą w stanie **Wysłane**.

W poniższej tabeli przedstawiono, jak zmienia się stan ZO podczas odbierania ofert i rejestrowania informacji w arkuszu odpowiedzi na ZO.

| **Akcja**                                               | **Najniższy stan wśród wszystkich wierszy we wszystkich ZO** | **Najwyższy stan wśród wszystkich wierszy we wszystkich ZO** | **Najniższy stan nagłówka sprawy ZO** | **Najwyższy stan nagłówka sprawy ZO** | **Najniższy stan wiersza sprawy ZO** | **Najwyższy stan wiersza sprawy ZO** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Rejestrowanie oferty jednego dostawcy w ZO i zapisywanie jej.        | Wysłany                                           | Odebrane                                        | Wysłany                              | Odebrane                           | Wysłany                            | Odebrane                         |
| Rejestrowanie oferty drugiego dostawcy w ZO i zapisywanie jej. | Odebrane                                       | Odebrane                                        | Odebrane                          | Odebrane                           | Odebrane                        | Odebrane                         |


W przykładzie poniżej widać najwyższy i najniższy stan w sprawie ZO, gdzie jedną ofertę otrzymano, a drugą ofertę zaakceptowano. Gdy otrzymana oferta zostanie odrzucona, najniższy stan zmieni się z Otrzymane na Odrzucone w nagłówku i wierszu sprawy ZO.


|            <strong>Akcja</strong>             | <strong>Najniższy stan wśród wszystkich wierszy we wszystkich ZO</strong> | <strong>Najwyższy stan wśród wszystkich wierszy we wszystkich ZO</strong> | <strong>Najniższy stan nagłówka sprawy ZO</strong> | <strong>Najwyższy stan nagłówka sprawy ZO</strong> | <strong>Najniższy stan wiersza sprawy ZO</strong> | <strong>Najwyższy stan wiersza sprawy ZO</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Zaakceptowanie jednej z ofert. (lub co najmniej jeden wiersz) |                          Odebrane                           |                           Zaakceptowana                           |                    Odebrane                    |                    Zaakceptowana                     |                   Odebrane                   |                   Zaakceptowana                    |
|           Odrzucenie wszystkich innych ofert.           |                          Odrzucona                           |                           Zaakceptowana                           |                    Odrzucona                    |                    Zaakceptowana                     |                   Odrzucona                   |                   Zaakceptowany                    |

