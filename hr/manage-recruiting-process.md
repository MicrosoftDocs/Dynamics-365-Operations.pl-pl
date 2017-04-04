---
title: "Zarządzanie procesem rekrutacji"
description: "W tym artykule opisano proces śledzenia czynności podczas rekrutacji, w tym działania związane z reklamowaniem wolnych stanowisk i rekrutacji kandydatów, śledzenie informacji o kandydatach i zgłoszeniach, prowadzenie rozmów kwalifikacyjnych z kandydatami oraz wybieranie jednego lub kilku kandydatów na wolne stanowiska w organizacji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>Zarządzanie procesem rekrutacji

W tym temacie opisano pojęcie rekrutacji można użyć do śledzenia etapy procesu rekrutacji, w tym dążeń zmierzających do reklamowania wakatów i rekrutacji kandydatów, śledzenie informacji kandydata i zgłoszenia, rozmów kwalifikacyjnych wnioskodawców i wyboru kandydatów jednego lub więcej pracowników na stanowiska w organizacji.

<a name="overview"></a>Przegląd
--------

Projekty rekrutacji pomagają organizować kroki, które należy wykonać podczas wypełniania wolnych stanowisk w firmie. Wnioskodawca jest osobą, która stosuje się do zatrudnienia dla przedsiębiorstwa.  Aplikacja jest wyrażenia zainteresowania w zatrudniony w przedsiębiorstwie wnioskodawcy i powiązana projektu rekrutacji wyraźne zainteresowanie otwarcia szczególne.  Jednemu wnioskodawcy mogą mieć wiele aplikacji w obrębie tej samej firmy lub między różnymi firmami w Twojej organizacji.

<a name="recruitment-projects"></a>Projekty rekrutacji
--------------------

Projekty rekrutacji umożliwiają rekrutację do śledzenia postępu w odniesieniu do napełniania jeden lub więcej otwartych pozycji.  Projekt rekrutacji identyfikuje działu oraz zadania, dla których jeden lub więcej pozycji są otwarte. Projekty rekrutacji również śledzą następuję informacji o wolnych stanowiskach:
-   Określona liczba wolnych stanowisk
-   Osoba zarządzająca rekrutacją oraz alternatywna osoba kontaktowa dla stanowiska
-   Data zatwierdzenia zapotrzebowania
-   Termin zgłoszenia
-   Prognozowana data rozpoczęcia

Projekt rekrutacji zawiera **Ofertę pracy** używaną w systemie **Samoobsługi pracownika** do reklamowanie wolnego stanowiska. Aby wyświetlić wolne stanowisko pracownikom, projekt rekrutacji musi mieć **Ofertę pracy**, pole **Wyświetl na ekranie samoobsługi pracownika** musi mieć wartość Yes, **Ostateczny termin zgłoszenia** musi być ustawiony na datę przyszłą, a projekt rekrutacji musi mieć **Stan projektu** Rozpoczęty. Poniższa tabela zawiera listę stanów projektu rekrutacji możliwe i ich opis.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Zaplanowano | Przygotowywane są rekrutację.  Rekrutacja nie rozpoczął dla tego projektu. |
| Rozpoczęta   | Zgłoszenia są obecnie przyjmowane na wolne stanowiska w tym projekcie.                    |
| Zakończono  | Wszystkie wolne stanowiska w tym projekcie zostały wypełnione.                                          |
| Anulowano  | Rekrutacja została anulowana dla tego projektu.                                           |

Rekruterzy mogą również rejestrować **multimedia** używane do reklamowania wolnych stanowisk za pomocą zewnętrznych punktów, a także śledzić **rozwój** dla projektu lub zgłoszenia.

<a name="applicants"></a>Kandydaci
----------

Wnioskodawca jest osobą, która ma zastosowanie do pracy w przedsiębiorstwie.  Wnioskodawcy są współużytkowane przez wszystkie podmioty prawne w organizacji, umożliwiając dużej puli talenty wyszukiwanie od. Można zachować kompetencje, odwołania, wymagania związane z zakwaterowaniem, dane osobowe kandydatów. Po utworzeniu rekordu kandydata jest tworzony rekord tej osoby w globalnej książce adresowej. Na stronie **Kandydat** można przesyłać następujące informacje globalnej książki adresowej dla osób, które są kandydatami:
-   Informacje adresowe
-   Informacje kontaktowe
-   Informacje identyfikacyjne
-   Szczegóły nazwiska
-   Informacje osobiste

## <a name="applications"></a>Aplikacje
Na stronie **Zgłoszenie** można rejestrować informacje pochodzące z otrzymanych podań o pracę. Aplikacja jest wnioskodawcy wyrażenia zainteresowania w stanowiska w organizacji.  Aby utworzyć aplikację, wnioskodawca musi już istnieć jako kandydata lub osoby w systemie.
Podania o pracę przesłane przez kandydata w sieci web są podaniami oczekiwanymi złożonymi w reakcji na ofertę pracy lub są podaniami złożonymi przez kandydata bez związku z ofertami. Podania oczekiwane są automatycznie kojarzone z projektem rekrutacyjnym, którego dotyczyło ogłoszenie. Podania bez związku z ofertami są kojarzone z projektem rekrutacji określonym w polu **Rekrutacja** na stronie **Parametry zasobów ludzkich**.
### <a name="application-status"></a>Stan zgłoszenia

Stan zgłoszenia wskazuje, w jakim miejscu procesu rekrutacji jest podanie o pracę. W poniższej tabel wymieniono możliwe stany zgłoszenia i ich opisy.

| Stan    | Wskazuje, że…                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Odebrano  | Data otrzymania zgłoszenia.                                                             |
| Potwierdzono | Do kandydata zostało wysłane powiadomienie w celu potwierdzenia przyjęcia jego zgłoszenia.            |
| Rozmowa kwalifikacyjna | Do kandydata może zostać wysłane zaproszenie na rozmowę kwalifikacyjną.                                     |
| Odrzucenie | Do kandydata może zostać wysłane pismo informujące o odrzuceniu podania o pracę.                                          |
| Anulowano  | Do kandydata może zostać wysłane potwierdzenie wypłaty. Ten stan jest przypisywany ręcznie. |
| Zatrudniono  | Do kandydata może zostać wysłana oferta zatrudnienia.                                         |

### <a name="correspondence-actions"></a>Akcje korespondencyjne

Akcja korespondencyjna dla **Zgłoszenia** określa szablon dokumentu lub wiadomości e-mail, który ma zostać użyty do komunikacji z kandydatem, który przesłał zgłoszenie. Można skojarzyć **zakładki zgłoszeń** z akcji korespondencyjnych pozwala używać wartości z aplikacji, projekt wnioskodawcy, rozmowy kwalifikacyjnej i rekrutacji ze stron w komunikacji z kandydatami.  **Szablony wiadomości e-mail w aplikacji** mogą być tworzone dla akcji korespondencyjnych szybko wysłać do wnioskodawców, którzy mają aplikacji za pomocą niektórych stan korespondencji akcji połączenia i wiadomości e-mail. Na przykład, może wysłać wiadomość e-mail z potwierdzeniem do wszystkich aplikacji z **stanu** odebrane i **akcję korespondencji** odebrane.  Po wysłaniu wiadomości e-mail, użytkownik może automatycznie aktualizować stan używanej aplikacji.

## <a name="application-routing"></a>Marszruta zgłoszenia

Jeśli zgłoszenie ma zostać przejrzane przez kilku pracowników, w celu zarządzania tym procesem można tworzyć listę obiegową pracowników na stronie **Marszruta zgłoszenia**.

## <a name="interviews"></a>Rozmowy kwalifikacyjne

**Rozmów kwalifikacyjnych z kandydatami** mogą być planowane z **aplikacje** strony.  Użyj **wysłać informacje o spotkaniu** przycisk Wyślij plik kalendarza z informacji o harmonogramie rozmowy kwalifikacyjnej do wnioskodawcy i ankieter.

## <a name="skill-mapping"></a>Mapowanie umiejętności

**Mapowanie umiejętności** i **Profile mapowania kwalifikacji** mogą służyć do identyfikowania kandydatów dopasowanych do wolnego stanowiska.

## <a name="hiring-applicants"></a>Zatrudnianie kandydatów

Kandydatów zatrudnia się na stronie **Zgłoszenia**. Po zatrudnieniu kandydata rekord zgłoszenia otrzymuje stan **Zatrudniony**, a rekord osoby w globalnej książce adresowej jest kojarzony z rekordem nowego pracownika. Zmiany w danych globalnej książki adresowej dla nowego rekordu pracownika są również wyświetlane w rekordzie kandydata. Może to pomóc zmniejszyć wprowadzania danych, jeśli kiedykolwiek nowego pracownika stosuje się na inne stanowisko w firmie.  Zatrudnić pracownika istniejących w nowe położenie, kliknij przycisk **zmienić położenie** w **stan aplikacji** listy rozwijanej inicjowanie procesu transferu.




