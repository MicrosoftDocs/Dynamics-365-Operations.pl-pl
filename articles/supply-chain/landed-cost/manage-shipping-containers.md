---
title: Zarządzaj kontenerami wysyłkowymi
description: W tym temacie opisano, jak pracować z kontenerami wysyłkowymi. Kontenery transportowe służą do grupowania towarów, które są fizycznie zgrupowane razem. Są również stosowane w przypadkach, gdy koszty muszą być podzielone tylko na te towary, zwykle dlatego, że są one fizycznie razem.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 62a19262f4101105654ff948cef634d825b22c4189c73eb236bd1a4730a412f5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734194"
---
# <a name="manage-shipping-containers"></a>Zarządzaj kontenerami wysyłkowymi

[!include [banner](../../includes/banner.md)]

Kontenery transportowe służą do grupowania towarów, które są fizycznie zgrupowane razem. Są również stosowane w przypadkach, gdy koszty muszą być podzielone tylko na te towary, zwykle dlatego, że są one fizycznie razem.

Aby wyświetlić i przetworzyć towary za pomocą strony kontenera wysyłkowego, przejdź do **Koszt z wyładunkiem \> Kontenery wysyłkowe \> Wszystkie kontenery wysyłkowe**. Na stronie **Wszystkie kontenery wysyłkowe** jest wyświetlona lista wszystkich dostępnych kontenerów wysyłkowych. Możesz używać przycisków w Okienku akcji do tworzenia, usuwania i pracy z kontenerami wysyłkowymi. Wybierz dowolny kontener wysyłkowy na liście, aby wyświetlić jego szczegóły na stronie **Kontenery wysyłkowe**.

W górnej części strony ze szczegółowymi informacjami o kontenerze wysyłkowym są wyświetlane informacje o kontenerze i kosztach. W sekcji **Wiersze** znajdują się folio, towary, zamówienia zakupu lub zamówienia przeniesienia dołączone do kontenera.

## <a name="action-pane"></a>Okienko akcji

Okienko akcji na stronie **Wszystkie kontenery wysyłkowe** i **Kontenery wysyłkowe** zawiera przyciski, które umożliwiają pracę z wybranym kontenerem wysyłkowym. Każdy przycisk wykonuje pojedynczą akcję. W okienku akcji znajdują się także karty, z których każdy z kolei zawiera zestaw powiązanych przycisków. Oprócz tych różnic wszystkie przyciski i karty opisane w poniższych podsekcjach są dostępne zarówno w widoku listy (to jest na stronie **Wszystkie kontenery wysyłkowe**), jak i w widoku szczegółowym (tj. na stronie **Kontenery wysyłkowe**).

### <a name="buttons-on-the-manage-tab"></a>Przyciski na karcie Zarządzanie

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Zarządzanie** w okienku akcji.

| Przycisk | Opisy |
|---|---|
| Księguj listę przychodu | Umożliwia zaksięgowanie listy przychodu lub wyświetlenie list dokumentów przyjęcia produktów dla wszystkich wierszy zamówienia zakupu w kontenerze wysyłkowym. Jeśli używane są przesyłki obejmujące wiele firm, dla każdej firmy otwierane jest nowe okno dialogowe księgowania listy przyjęć. |
| Księguj dokument przyjęcia produktów | Zaksięguj pokwitowanie produktu dla wszystkich wierszy kontenera wysyłkowego. |
| Księguj fakturę | Opublikuj fakturę dla wszystkich wierszy zamówień w kontenerze wysyłkowym. W przypadku wysyłek obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania faktur dla każdej firmy. |
| Wyślij zamówienie przeniesienia | Zaksięguj przesyłkę z poleceniem przeniesienia dla wszystkich wierszy zamówienia przeniesienia w kontenerze wysyłkowym. W oknie dialogowym są wyświetlane tylko te wiersze kontenera wysyłkowego, które są typu zamówienie przeniesienia. |
| Przyjmuj zamówienie przeniesienia | Zaksięguj potwierdzenie przelewu dla wszystkich wierszy zamówienia w kontenerze wysyłkowym. Okno dialogowe odbioru to najprostszy sposób odbioru towarów w kontenerze wysyłkowym lub podczas podróży i jest jedną z trzech dostępnych opcji. Można też odbierać przy użyciu arkuszy przybycia lub przetwarzania urządzeń przenośnych. |
| Utwórz arkusz przyjęcia | Arkusz przybycia do organizacji można wygenerować za pomocą zaawansowanych funkcji magazynu. Dostępne opcje to: _Zaimicjuj ilość_ (zalecane), a następnie _Utwórz z towarów w drodze_ lub _Utwórz na pomocą zamówień zakupu_. Ostatnie dwie opcje zależą od tego, czy jest używane przetwarzanie towarów w drodze. |
| Zmień nazwę | Umożliwia otwarcie okna dialogowego, w którym można zmienić nazwę wybranego kontenera wysyłkowego. |
| Zmień szablon podróży | Zmień szablon podróży. Po zmianie szablonu wyjazdu może być konieczne wybranie opcji **Znajdź automatyczne koszty** lub ręcznie dodaj koszty ponownie, ponieważ koszty wysyłki zostaną usunięte. |
| Konwertuj na wynajem | Skonwertuj wybrany kontener wysyłkowy na wynajęty kontener wysyłkowy. |

### <a name="buttons-on-the-general-tab"></a>Przyciski na karcie Ogólne

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Ogólne** w okienku akcji.

| Przycisk | Opisy |
|---|---|
| Lista przychodu | Opublikuj listę przyjęć dla wszystkich wierszy zamówienia zakupu w kontenerze wysyłkowym. Jeśli używane są podróże obejmujące wiele firm, dla każdej firmy otwierane jest nowe okno dialogowe księgowania listy przyjęć. |
| Dokument przyjęcia produktów | Umożliwia wyświetlenie rekordu dokumentu przyjęcia produktów, jeśli jest używany. Proces przyjęcia produktów będzie używany tylko w przypadku, gdy dla towarów nie są używane funkcje dotyczące towarów w drodze. |
| Przyjęcie pozycji | Umożliwia wyświetlenie arkusza przybycia towaru dla kontenera wysyłkowego, jeśli jest używany ten arkusz. |
| Etapy | Stopy są używane do identyfikowania oddzielnych części podróży. Czasy realizacji można skojarzyć z każdym etapem, aby ułatwić śledzenie wysyłki. Aby uzyskać więcej informacji, zobacz temat [Konfiguracja podróży wieloetapowej](multi-leg-journey-setup.md). |
| Śledzenie | Przeglądanie i aktualizowanie śledzenia wysyłki. |
| Zamówienia towaru w drodze | Stronę **Towary w drodze** można otworzyć bezpośrednio z kontenera. Ta strona pokazuje rekordy towarów w drodze tylko dla wybranego kontenera wysyłkowego. |

## <a name="header-view"></a>Widok nagłówka

Aby otworzyć widok **Nagłówek**, otworzyć kontener wysyłkowy, a następnie wybrać kartę **Nagłówek** w prawym górnym rogu nagłówka kontenera wysyłkowego.

### <a name="settings-on-the-general-fasttab"></a>Ustawienia na skróconej karcie Ogólne

W poniższej tabeli opisano ustawienia dostępne na skróconej karcie **Ogólne** w widoku **Nagłówka** kontenera wysyłkowego.

| Pole | opis |
|---|---|
| Kontener wysyłkowy | Nazwa kontenera wysyłkowego. |
| Podróż | Podróży skojarzonej z kontenerem wysyłkowym. |
| Typ kontenera wysyłkowego | Wprowadź typ kontenera wysyłkowego. To pole musi być ustawione. Można go użyć do określenia kosztu transportu, na przykład przez wybranie kosztu automatycznego skojarzonego z typem kontenera wysyłkowego. |
| Statek | Wprowadź lub wybierz środek transportu. Jeśli środek transportu nie jest wymieniony jako wartość, można wprowadzić identyfikator statku jako tekst wolny. W takim przypadku główna tabela nie jest aktualizowana, aby można było później wybrać w tym polu identyfikator statku. Aby uzyskać więcej informacji, zobacz [Statki](shipping-information-setup.md#vessels). |
| Typ jednostki | Typy jednostek są używane jako dodatkowy środek grupowania i identyfikowania kontenerów wysyłkowych. Są one wyświetlane i wybierane na stronie kontenera wysyłkowego. Aby uzyskać więcej informacji, zobacz [Skonfiguruj typy jednostek](shipping-container-setup.md#unit-types). |
| Typ systemu chłodzenia | Typy chłodnicze są używane jako dodatkowy sposób grupowania i identyfikacji kontenerów transportowych, zwykle kontenerów chłodniczych. Są one wyświetlane i wybierane na stronie kontenera wysyłkowego. Aby uzyskać więcej informacji, zobacz [Skonfiguruj typy chłodnictwa](shipping-container-setup.md#refrigeration-types). |
| Miara | To pole umożliwia wyświetlanie miary określonej w module **Koszt z wyładunkiem**. Pomiary są często używane przez organizacje, które nie znają indywidualnej objętości lub wagi towarów, ale wymagają dokładniejszego podziału niż ilość lub ilość. Spedytor poda wagę w kilogramach lub miarkę sześcienną i możesz ją umieścić na poziomie towaru lub zamówienia. Może być aktualizowany automatycznie, jeśli parametr jest wybrany, lub może zostać wprowadzony ręcznie. |
| Jednostka miary | Jednostka miary, która ma zastosowanie do numeru w polu **Miara**. |
| Rzeczywista waga | Można zarejestrować rzeczywistą wagę kartonu lub kontenera. Ta wartość może być używana do weryfikacji w stosunku do maksymalnej wagi dozwolonej w konfiguracji kontenera wysyłkowego. |
| Liczba kartonów | W przypadku ustawienia parametru liczba kartonów jest aktualizowana automatycznie. |
| Opis towarów | Opis towarów można wybrać w kontenerze wysyłkowym lub nagłówku folio. Służy do identyfikacji podróży, kontenera wysyłkowego lub folio towarów. Aby uzyskać więcej informacji, zobacz temat [Opis towaru](shipping-information-setup.md#description-of-goods). |
| Spedytorski lotniczy list przewozowy/list przewozowy | Możesz określić spedytorski lotniczy list przewozowy lub list przewozowy dla kontenera wysyłkowego. |
| Uwagi | Dodatkowe informacje dotyczące kontenera wysyłkowego. |
| Z możliwością zwrotu | Wartość wskazująca, czy kontener wysyłkowy może zostać zwrócony po podróży. |
| Stan podróży | Status podróży powiązanej z kontenerem wysyłkowym. |
| Stan zamówienia zakupu | Stan zamówienia zakupu, które jest powiązane z kontenerem wysyłkowym. |

### <a name="settings-on-the-delivery-fasttab"></a>Ustawienia na skróconej karcie Dostawa

W poniższej tabeli opisano ustawienia dostępne na skróconej karcie **Dostawa** w widoku **Nagłówka** kontenera wysyłkowego.

| Pole | opis |
|---|---|
| Data i godzina utworzenia | Data i godzina utworzenia kontenera. |
| Ex-factory — data | Data ta jest zwykle podawana fabryce / sprzedawcy w celu wskazania, kiedy spodziewasz się, że towary opuściły jej teren. Kiedy pracujesz z fabryką w Azji, ta data jest często wymagana zamiast daty, do której spodziewasz się, że towary zostaną dostarczone. (Z kolei w przypadku dostawy lokalnej wymagana jest data spodziewanego terminu dostawy towarów). To pole można wypełnić w wierszach zamówienia zakupu na liście kontenerów wysyłkowych. Możesz również wprowadzić go tutaj ręcznie. |
| Data wysyłki | Tę datę można wydrukować na dokumencie zamówienia zakupu. Zazwyczaj informuje ono fabrykę/dostawcę o terminie dostarczenia towarów do portu w terminie. To pole jest używane wyłącznie w celach informacyjnych. Nie jest używane do szacowania oczekiwanej daty dostawy towarów w kontenerze wysyłkowym. W tym polu można ustawić, że strona kontroli śledzenia jest aktualizowana automatycznie. |
| Data przekazania do magazynu | Najwcześniejsza data, z kiedy towary z zamówień zakupu, które są połączone z podróży, będą dostępne do sprzedaży.|
| Szacowana data dostawy | Zazwyczaj termin przybycia towarów do magazynu. To pole jest używane wyłącznie w celach informacyjnych. Nie jest używane do obliczania planowania głównego w wierszach zamówienia zakupu w kontenerze wysyłkowym. Oczekiwana data dostawy w wierszach zamówienia zakupu jest aktualizowana przy użyciu kontroli śledzenia. To pole można skonfigurować tak, aby było aktualizowane po zaktualizowaniu strony kontrolnej śledzenia. |
| Data wyjazdu | Zazwyczaj data, gdy samolot lub statek faktycznie opuszcza port zamorski. |
| Szacowany czas przybycia w porcie wysyłki | Szacowana data przybycia do portu docelowego („do” portu). |
| Otrzymano oryginalne dokumenty | Opcjonalnie: zaktualizuj datę, kiedy otrzymano oryginalne dokumenty. |
| Polecony broker | Opcjonalnie: zaktualizuj datę poinformowania brokera. |
| Oryginalny list przewozowy został wysłany | Opcjonalnie: zaktualizuj datę wysłania oryginalnego listu przewozowego. |
| Zwolnione towary | Opcjonalnie: Zaktualizuj datę wydania towarów. |
| Termin odbiorcy | Opcjonalnie: zaktualizuj datę terminu dla odbiorcy. |
| Dostarczono do magazynu | Opcjonalnie: zaktualizuj datę dostarczenia towarów do magazynu. |
| Data weryfikacji | Opcjonalnie: zaktualizuj datę weryfikacji. |
| Instrukcje dotyczące dostawy | Opcjonalnie: zaktualizuj datę instrukcji dostawy. |
| Port źródłowy | Port, z którego zostaną wysłane produkty. |
| Port docelowy | Port, do którego zostaną wysłane produkty. |
| Lokalny spedytor | To pole jest używane wyłącznie w celach informacyjnych. Lokalną usługę przesyłania dalej można wybrać z tabeli dostawców. |
| Data lokalnego transportu | Umożliwia wprowadzenie daty rezerwacji transportu lokalnego. To pole może ułatwić planowanie magazynu. |
| Godzina lokalnego transportu | Wprowadź przedział czasu. To pole może ułatwić planowanie magazynu. |
| Szablon podróży | Szablon podróży określony dla podróży. Szablon podróży zawiera szczegóły portów „do” i „od” oraz czasy realizacji skojarzone z kontrolą śledzenia kontenera wysyłkowego. |

### <a name="settings-on-the-other-fasttab"></a>Ustawienia na skróconej karcie Inne

W poniższej tabeli opisano ustawienia dostępne na skróconej karcie **Inne** w widoku **Nagłówka** kontenera wysyłkowego.

| Pole | opis |
|---|---|
| Wynajem | Wartość wskazująca, czy kontener wysyłkowy jest wynajętym kontenerem wysyłkowym. Koszty wynajmu mogą być skojarzone z kontenerami wynajmu. |
| Przekonwertowane na wynajem | Wartość wskazująca, czy kontener wysyłkowy został przekształcony w kontener wysyłkowy do wypożyczenia. Koszty wynajmu mogą być skojarzone z kontenerami wynajmu. |
| Oryginalna podróż | Jeśli kontener transportowy został przeniesiony na nową podróż, pierwotny rejs. |
| Wykorzystano | Skorzystaj z tego, aby odnotować, czy użyto wynajmowanego kontenera transportowego. Służy wyłącznie do celów informacyjnych. |
| Oczekiwana data załadunku | Oczekiwana data załadowania kontenera wysyłkowego towarami. |
| Nasz numer seryjny | Służy do wprowadzania numeru seryjnego używanego wewnętrznie przez firmę dla kontenera wysyłkowego. |
| Numer seryjny firmy przewozowej | Umożliwia wprowadzenie numeru seryjnego dostarczonego przez firmę przewozową lub agenta dla kontenera wysyłkowego. |
| Data zastosowania certyfikatu egzaminu | Data wniosku o badanie kontenera wysyłkowego. |
| Data otrzymania certyfikatu egzaminu | Data, kiedy otrzymano certyfikat badania. |
| Data wygaśnięcia certyfikatu egzaminu | Data wygaśnięcia certyfikatu egzaminacyjnego. |
| Identyfikator certyfikatu egzaminu | Numer certyfikatu wydanego po zakończeniu badania. |

## <a name="lines-view"></a>Widok wierszy

Aby otworzyć widok **Wiersze**, otworzyć kontener wysyłkowy, a następnie wybrać kartę **Wiersze** w prawym górnym rogu nagłówka kontenera wysyłkowego.

### <a name="information-on-the-shipping-container-fasttab"></a>Informacje na skróconej karcie kontenera wysyłkowego

Skrócona karta **Kontenera wysyłkowego** w widoku **Wierszy** zawiera informacje o folio. Większość z tych informacji będzie też wyświetlana w widoku **Nagłówek**, zgodnie z opisem opisanym powyżej w tym temacie.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informacje i przyciski na skróconej karcie Wiersze

Skrócona karta **Wiersze** w widoku **Wiersze** zawiera szczegóły dotyczące poszczególnych pełnych lub częściowych wierszy zamówienia zakupu zawartych w bieżącym kontenerze wysyłkowym.

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na skróconej **Wiersze** w widoku **Wiersze**.

| Przycisk | opis |
|---|---|
| Usuń | Usuń wybrany wiersz zamówienia zakupu z podróży. |
| Zapasy \> Transakcje | Wyświetl transakcje magazynowe dla wybranej linii zamówienia zakupu. Pamiętaj, że jeśli używasz towarów w transporcie, wyświetlane jest również oryginalne zamówienie i zamówienia towarów w transporcie. |
| Zapasy \> Wyświetl wymiary | Umożliwia otwarcie okna dialogowego, w którym można wybrać wymiary magazynowe wyświetlane dla wyświetlanych transakcji. |
| Odśwież | Zaktualizuj informacje związane z kwotą, wagą lub objętością wiersza wybranego wiersza zamówienia zakupu. |

### <a name="information-on-the-lines-details-fasttab"></a>Informacje na skróconej karcie Wiersze

Skrócona karta **Szczegóły wiersza** w widoku **Wiersze** pokazuje więcej informacji o wierszu zamówienia zakupu, który jest aktualnie wybrany na skróconej karcie **Wiersze**.
