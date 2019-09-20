---
title: Tworzenie, zatwierdzanie i podpisywanie ofert
description: W tym temacie szczegółowo wyjaśniono sposób tworzenie, zatwierdzania i podpisywania oferty dla kandydata w Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8c5f95f1d3be22a73cc42cb3667b793490f2a136
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739640"
---
# <a name="create-approve-and-sign-offers"></a>Tworzenie, zatwierdzanie i podpisywanie ofert

[!include[banner](../includes/banner.md)]

W wielu przypadkach przygotowanie pakietu oferty dla kandydata musi się odbyć bardzo szybko.
Korzystanie z szablonów skonfigurowanych przez administratora aplikacji Attract zmniejszy nakład czasu i pracy, jaki twórcy ofert muszą poświęcić na przygotowywanie i wysyłanie ofert kandydatowi.

## <a name="create-an-offer"></a>Tworzenie oferty

Po włączeniu aplikacji Zarządzanie ofertami każdy użytkownik mający rolę Menedżer zatrudniający lub Osoba rekrutująca może przygotować pakiet oferty dla kandydata. Aby przygotować ofertę, wykonaj następujące czynności.

1.  Przejdź do funkcji i zgłoszenia kandydata, dla którego tworzysz ofertę.

1.  Przejdź do okna **Etap oferty** i kliknij przycisk **Przygotuj ofertę**.

    Nastąpi przekierowanie do aplikacji Oferta, gdzie zobaczysz kandydata o stanie **Nowy**. Zobaczysz także inne oferty, w których tworzeniu współuczestniczysz jako twórca lub osoba zatwierdzająca.

1.  Kliknij przycisk **Przygotuj ofertę**. 
    
    Zobaczysz zbiór różnych pakietów ofert udostępnionych przez administratora.

1.  Zaznacz pakiet i kliknij przycisk **Gotowe**, aby rozpocząć przygotowywanie oferty.

    Zostanie załadowany szablon pakietu oferty, w którym będą wypełnione pola danych funkcji i kandydata.

1.  Wszystkie symbole zastępcze danych oferty, które wchodzą w skład pakietu oferty, są widoczne na stronie docelowej. Na tej stronie można wypełnić wszystkie pola wartości z całego pakietu.

    Na stronie docelowej widać także wszystkie szablony dokumentów oferty wchodzących w skład pakietu oferty.

1.  W zależności od tego, jak szablon został skonfigurowany przez administratora, na tym etapie może być możliwe edytowanie zawartości oferty.

1.  Jeśli trzeba usunąć dokumenty oznaczone jako niewymagane, możesz to zrobić.

1. Gdy wszystkie symbole zastępcze danych oferty zostaną wypełnione, kliknij przycisk **Zapisz**, aby zapisać wersję roboczą oferty.

>[!NOTE]
> Po zapisaniu wersji roboczej można usunąć wersję roboczą oferty lub w razie potrzeby wybrać nowy szablon pakietu.


## <a name="approve-an-offer"></a>Zatwierdzanie oferty

Większość ofert musi przejść przez proces zatwierdzania, aby uzyskać pewność, że oferta spełnia wymagane normy. Jeśli oferta nie spełnia standardów, na przykład jeśli twórca oferty nie przestrzegał reguł danych oferty i zastąpił wartości w ofercie, proces zatwierdzania będzie wymagany. Aby wysłać ofertę do zatwierdzenia, należy wykonać następujące czynności.

1.  Gdy oferta jest w stanie wersji roboczej, dodaj osoby zatwierdzające w **panelu osób zatwierdzających**. 
    >[!NOTE]
    > Menedżerowie zatrudniający są domyślnie dodawani jako osoby zatwierdzające. Jako osobę zatwierdzającą dla oferty można wybrać dowolnego użytkownika z organizacji.

1.  W razie potrzeby przypisz osoby zatwierdzające do zatwierdzania sekwencyjnego lub równoległego. Ta opcja będzie dostępna tylko wtedy, jeśli została skonfigurowana przez administratora.
    >[!NOTE]
    > Jeśli proces zatwierdzania ma charakter sekwencyjny, w razie potrzeby można edytować kolejność osób zatwierdzających.

1.  Po zakończeniu definiowania łańcucha zatwierdzania można zmodyfikować zawartość wiadomości e-mail o zatwierdzeniu, a następnie wysłać powiadomienie do osób zatwierdzających. Kliknij przycisk **Wyślij do osób zatwierdzających**.
    >[!NOTE]
    > Jeśli oferta była niestandardowe, musisz podać uzasadnienie.

1.  Jeśli twórca oferty postanowi pominąć osobę zatwierdzającą, może wprowadź o tym notatkę, a następnie przekazać ofertę do następnej osoby zatwierdzającej.

Osoby zatwierdzające otrzymają wiadomość e-mail z prośbą o zatwierdzenie oferty. Wtedy mogą kliknąć łącze w wiadomości e-mail i otworzyć ofertę, sprawdzić cały pakiet oferty, a następnie zatwierdzić pakiet albo odesłać z powrotem do autora oferty. Osoby zatwierdzające oferty muszą dodać osobną notatkę, jeśli odrzucą pakiet oferty i skierują go do dalszych modyfikacji. 

W przypadkach, gdy zostanie utworzona nowa wersja oferty, zanim osoba zatwierdzająca zakończy sprawdzanie, osoba zatwierdzająca nie będzie mogła zatwierdzić ani odrzucić oferty.

## <a name="offer-versioning"></a>Przechowywanie wersji oferty 

Gdy oferta zostanie zatwierdzona lub odesłana do dalszych poprawek, możesz wybrać opcję **Włącz edytowanie** i utworzyć nową wersję oferty. Nowa wersja oferty zawiera wszystkie wartości danych oferty oraz listę osób zatwierdzających przeniesione z ostatniej wersji. 

Osoby zatwierdzające mogą przełączać między różnymi wersjami oferty, jeśli zostały im one udostępnione do zatwierdzenia. Ponadto osoba zatwierdzająca lub twórca oferty może usunąć wybraną wersję roboczą oferty, aby wrócić do poprzedniego stanu.


## <a name="send-an-offer-to-a-candidate"></a>Wysyłanie oferty do kandydata 

Gdy oferta jest zapisana, zatwierdzona i gotowa do wysłania do kandydata, kliknij przycisk **Wyślij do kandydata**.

Istnieje kilka czynności, które można wykonać przed wysłaniem oferty do kandydata.
-  Można wyświetlić listę dokumentów wchodzących w skład pakietu oferty, który zostaną wysłane do kandydata.

-  Można określić datę ważności oferty. Kandydaci muszą zaakceptować lub odrzucić ofertę przed upływem jej daty ważności.  Kandydat otrzyma przypomnienia 48 godzin przed upływem daty ważności oferty.

-  Mogą istnieć dodatkowe dokumenty, które chcesz dołączyć do procesu akceptacji oferty. Będzie można wyświetlić listę typów wymaganych dokumentów.

- Opcja e-podpisu: są dwa sposoby połączenia dostawcy e-podpisu wybranego przez użytkownika. Przejdź do **Ustawień użytkownika** w **Ofercie** w menu **Połączenia**, aby połączyć się z **Adobe Sign** lub **DocuSign**. Alternatywnie pojawi się monit o połączenie strony **wysłania oferty do kandydata**, jeśli połączenie nie zostało jeszcze utworzone na podstawie ustawień użytkownika. Konto e-podpis trzeba połączyć tylko raz. Ta sama licencja użytkownika jest używana do wszystkich przyszłych pakietów ofert wysyłanych przez tego samego użytkownika. 

### <a name="adobe-sign"></a>Adobe Sign
Jeśli wybrano Adobe Sign jako preferowaną metodę e-podpisu, twórcy ofert muszą na tym etapie połączyć swoją licencję Adobe Sign. 

### <a name="docusign"></a>DocuSign
Jeśli wybrano DocuSign jako preferowaną metodę e-podpisu, twórcy ofert muszą na tym etapie połączyć swoją licencję DocuSign. Po zalogowaniu się domyślne konto i uprawnienia skojarzone z profilem użytkownika DocuSign są połączone z Talent Attract. 

-  Można wyświetlić i edytować szablon wiadomości e-mail zgodnie z potrzebami.

Gdy oferta jest gotowa i klikniesz przycisk **Wyślij do kandydata**, kandydat otrzyma wiadomość e-mail z informacją, że oferta czeka na przeczytanie.

>[!NOTE]
> Jeśli używasz Adobe Sign lub DocuSign i wystąpi błąd podczas wysyłania oferty do kandydata, spróbuj rozłączyć i ponownie połączyć konto użytkownika e-podpisu w **Ustawieniach użytkownika**. Jeśli ten problem będzie nadal występował, skontaktuj się z naszą pomocą techniczną, używając łącza **Zgłoś problem**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Czynności wykonywane przez kandydata po otrzymaniu oferty

Gdy kandydat zostanie powiadomiony, że została mu udostępniona oferta, może kliknąć łącze w otrzymanej wiadomości e-mail, przejść do pulpitu nawigacyjnego zgłoszeń i wyświetlić ofertę. Pulpit nawigacyjny będzie pokazywał kandydatowi wszystkie działania, które nadal trzeba wykonać.

1.  Aby wyświetlić ofertę i wszystkie pokrewne dokumenty, kandydat musi kliknąć przycisk **Wyświetl ofertę**.

    Kandydaci mogą również pobrać pakiet oferty w formacie .zip.

1.  Aby zaakceptować ofertę, kandydat musi kliknąć przycisk **Przejdź do podpisu** dla każdego dokumentu wchodzącego w skład pakietu oferty.

1.  Gdy wszystkie dokumenty zostaną indywidualnie podpisane i zaakceptowane, kandydat musi wybrać opcję zakończenia procesu akceptacji, klikając przycisk **Zaakceptuj ofertę** u góry strony.

1.  Aby odrzucić ofertę, kandydat musi kliknąć opcję **Odrzuć ofertę** u góry strony, wybrać odpowiedni powód, w razie potrzeby dodać komentarz, a następnie kliknąć przycisk **Odrzuć**.

1.  Po zaakceptowaniu lub odrzuceniu oferty kandydat może pozostać w widoku oferty albo wrócić do pulpitu nawigacyjnego zgłoszeń.

1.  Jeśli w ramach procesu akceptacji oferty pojawiły się wnioski o inne dokumenty, kandydat powinien przekazać żądane dokumenty i oznaczyć je względem żądanych typów dokumentów.

1.  Twórca oferty zostanie powiadomiony, gdy wszystkie dokumenty zostaną przekazane, a pakiet oferty podpisany.


## <a name="withdrawing-an-offer"></a>Wycofywanie oferty

Ofertę można wycofać od kandydata w dowolnym momencie z różnych przyczyn. 
1.  W celu wycofania oferty kliknij przycisk wielokropka (**...**), a następnie kliknij przycisk **Wycofaj ofertę**. 

2. Pojawi się komunikat z pytaniem, czy skontaktowano się z kandydatem w sprawie zmiany stanu. Jeśli z kandydatem jeszcze się nie skontaktowano, zobaczysz opcję wysłania kandydatowi wiadomości e-mail z informacją o dalszych czynnościach. 

   Oferta przestanie być dostępna dla kandydata.


## <a name="closing-an-offer"></a>Zamykanie oferty 

Gdy oferta zostanie zaakceptowana, odrzucona lub wycofana bez konieczności podejmowania dalszych kroków, możesz zamknąć ofertę, tak aby w tym pakiecie oferty nie można było wprowadzać żadnych dalszych zmian.
