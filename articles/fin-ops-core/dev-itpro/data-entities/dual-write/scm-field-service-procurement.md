---
title: Integracja zaopatrzenia między aplikacjami Supply Chain Management i Field Service
description: W tym temacie opisano, w jaki sposób integracja podwójnego zapisu obsługuje tworzenie i aktualizacje zamówień zakupu zarówno z aplikacji Supply Chain Management i Field Service.
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 4a2420981553957b6b234fe56747bc6f3568acf6b8ad77366c33caeae63b4faf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716766"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Integracja zaopatrzenia między aplikacjami Supply Chain Management i Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Aplikacja Microsoft Dynamics 365 Supply Chain Management oferuje zaawansowane funkcje zaopatrzenia. Aplikacja Dynamics 365 Field Service oferuje podobne funkcje, które obsługują procesy zakupów skojarzone z procesem usług. Funkcjonalność tych dwóch aplikacji jest zintegrowana za pośrednictwem podwójnego zapisu, a wynikające z nich międzyfunkcjonalne przypadki użycia są włączane za pomocą mapowań tabel, logiki rozwiązań, widoków i formularzy.

Integracja ta obsługuje tworzenie zamówień zakupu, a w większości przypadków aktualizacje z obu aplikacji. Aplikacja Supply Chain Management kontroluje natomiast ceny, adresy i przyjęcia produktów. Kilka rozbudowanych przypadków użycia obejmujących wiele funkcji jest włączonych dla organizacji, które korzystają z aplikacji Field Service i Supply Chain Management. Umożliwiają one włączanie i śledzenie zaopatrzenia na obu platformach.

Na poniższej ilustracji przedstawiono tabele na obu platformach oraz sposób ich wzajemnego mapowania. Zamówienia zakupu w usłudze Field Service odwołują się do wiersza *konta*, podczas gdy zamówienia zakupu w aplikacji Supply Chain Management odwołują się do wiersza *dostawcy*. Aby rozwiązać ten problem, w przypadku podwójnego zapisu odwołanie jest używane do łączenia wierszy *dostawcy* z wierszami *konta*. Aby uzyskać więcej informacji, zobacz temat [Zintegrowane dane główne dostawcy](vendor-mapping.md)

![Mapowania zaopatrzenia.](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Wymagania wstępne

Aby zintegrować aplikację Supply Chain Management z usługą Field Service, należy zainstalować następujące składniki:

- Wersja usługi Field Service 8.8.31.60 lub nowsza w celu kompleksowej integracji zamówień zakupu
- Supply Chain Management w wersji 10.0.14 lub nowszej
- Podwójny zapis, aby uruchomić rozwiązanie OneFSSCM

## <a name="installation-guidelines"></a>Wytyczne dotyczące instalacji

### <a name="prerequisites"></a>Wymagania wstępne

- **Podwójny zapis** — aby uzyskać więcej informacji, zobacz temat [Strona główna podwójnego zapisu](dual-write-home-page.md#dual-write-setup).
- **Dynamics 365 Field Service** — aby uzyskać więcej informacji, zobacz temat [Jak zainstalować aplikację Dynamics 365 Field Service](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Gdy są one włączone w usłudze Microsoft Dataverse, podwójny zapis i usługa Field Service wprowadzają kilka warstw rozwiązania rozszerzających środowisko o nowe metadane, formularze, widoki i logikę. Te rozwiązania można włączyć w dowolnej kolejności, chociaż instalacja jest zazwyczaj przeprowadzana w podanej tutaj kolejności:

1. **Field Service Common** — rozwiązanie Field Service Common jest instalowane, gdy w środowisku jest zainstalowana usługa Field Service.
2. **Field Service (Anchor)** — rozwiązanie Field Service (Anchor) jest instalowane, gdy w środowisku jest zainstalowana usługa Field Service. 
3. **Rozszerzona aplikacja Supply Chain Management** — rozszerzona aplikacja Supply Chain Management jest instalowana automatycznie, gdy w środowisku jest włączona funkcja podwójnego zapisu. 
4. **Rozwiązanie OneFSSCM** — rozwiązanie OneFSSCM jest instalowane automatycznie przez ostatnie zainstalowane rozwiązanie (Field Service lub Supply Chain Management).

    - Jeśli usługa Field Service jest już zainstalowana w środowisku i zostanie uaktywniona funkcja podwójnego zapisu, która instaluje rozszerzona aplikację Supply Chain Management, instalowane jest rozwiązanie OneFSSCM.
    - Jeśli rozszerzona aplikacja Supply Chain Management jest już zainstalowana w środowisku i zostanie zainstalowana aplikacja Field Service, instalowane jest rozwiązanie OneFSSCM.

## <a name="initial-synchronization"></a>Wstępna synchronizacja

Aby utworzyć nowe zamówienia zakupu i pracować z istniejącymi zamówieniami zakupu, należy zsynchronizować dane referencyjne między aplikacją Supply Chain Management i usługą Dataverse. Początkowej funkcji zapisu można użyć do wykrywania relacji tabel i znajdowania tabel, które należy włączyć dla danej mapy.

Należy zsynchronizować następujące tabele:

- Szablony produktów

    Po uruchomieniu początkowego zapisu zostanie wyświetlona pełna lista wymaganych tabel. Oto kilka z tych szablonów:

    - Wszystkie produkty
    - Zwolnione produkty (wersja 2)
    - Dataverse odrębne produkty zwolnione w usłudze CDS

- Oddziały
- Magazyny
- Szablony kategorii zaopatrzenia

    Oto kilka z tych szablonów:

    - Kategorie zaopatrzenia
    - Pro
    - Hierarchia kategorii produktów
    - Przypisania kategorii produktów

- Szablony dostawców, takie jak Dostawca (wersja 2)
- Szablony osób kontaktowej, takie jak Osoby kontaktowe usługi Dataverse (wersja 2)
- Szablony pracowników, takie jak Pracownik

Synchronizacja tabel zapewnia, że wszystkie dokumenty (zamówienia zakupu i dokumenty przyjęcia produktów) w aplikacji Supply Chain Management są dostępne w programie Dataverse.

### <a name="account-and-vendor-tables"></a>Tabele Konto i Dostawca

Zamówienia zakupu w usłudze Field Service śledzą dostawców przy użyciu tabeli Konto. Dlatego tabele Dataverse dla zamówień zakupu używają kont do śledzenia dostawców. Aby uwzględnić tę kluczową różnicę, należy aktywować następujące cztery przepływy pracy, aby konta i dostawcy były zsynchronizowane: 

- Tworzenie dostawców w tabeli kont
- Tworzenie dostawców w tabeli dostawców
- Aktualizowanie dostawców w tabeli kont
- Aktualizowanie dostawców w tabeli dostawców

Jeśli zainstalowano rozwiązanie OneCM, przepływy pracy są aktywowane automatycznie, ponieważ są zainstalowano aplikacje Field Service i Supply Chain Management Extended. Jeśli usługa Field Service nie jest zainstalowana, ale chcesz zintegrować z nią tabele zamówień zakupu usługi Dataverse, należy aktywować te przepływy pracy. W obu przypadkach, o ile nie rozpoczniesz się od początku, przed utworzeniem zamówień zakupu konieczne może się okazać utworzenie kont Dataverse dla wszystkich dostawców. W przeciwnym razie mogą wystąpić błędy.

### <a name="initial-synchronization"></a>Wstępna synchronizacja

Gdy wszystkie warunki wstępne są spełnione, aby istniejące zamówienia zakupu i przyjęcia produktów były dostępne na obu platformach, należy wykonać wstępną synchronizację następujących szablonów:

- Nagłówek zamówienia zakupu (wersja 2)
- Wiersz zamówienia zakupu CDS
- Usunięcie nietrwałe wiersza zamówienia zakupu CDS
- Przyjęcie zamówienia zakupu
- Przyjęcie zamówienia zakupu — produkt

## <a name="mappings-with-logic"></a>Mapowania z logiką

Integracja zaopatrzenia rozszerza mapowanie produktów o następującą logikę, aby kolumna **Typ produktu usługi Field Service** była poprawnie ustawiona w tabeli produktów w usłudze Dataverse:

- Jeśli **typ produktu** ma wartość *Produkt*, a opcja **Grupa modeli produktów i towarów, Produkt magazynowany** ma wartość *Prawda*, pole **Typ produktu usługi Field Service** jest ustawione na *Zapasy*.
- Jeśli **typ produktu** ma wartość *Produkt*, a opcja **Grupa modeli produktów i towarów, Produkt magazynowany** ma wartość *Fałsz*, pole **Typ produktu usługi Field Service** jest ustawione na *Poza zapasami*.
- Jeśli **typ produktu** ma wartość *Usługa*, pole **Typ produktu usługi Field Service** ma wartość *Usługa*.

Ponadto usługa Dataverse zawiera logikę mapowania dostawców z ich kontami pokrewnymi. Ta logika ustawia domyślne konto dostawcy faktury. Podczas tworzenia logika dodatku po stronie serwera ustawia domyślne konto dostawcy dla faktury na podstawie dostawcy, który jest powiązany z tym kontem. Dostawca ma odwołanie do konta faktury, które jest używane do ustawienia tej wartości.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze

- Zamówienia zakupu mogą być tworzone i aktualizowane przez użytkowników usługi Dataverse. Jednak proces i dane są kontrolowane przez aplikację Supply Chain Management. Ograniczenia dotyczące aktualizacji kolumn zamówienia zakupu w Supply Chain Management mają zastosowanie, gdy aktualizacje pochodzą z usługi Field Service. Na przykład nie można zaktualizować zamówienia zakupu, jeśli zostało ono sfinalizowane. 
- Jeśli zamówienie zakupu jest kontrolowane przez zarządzanie zmianami w Supply Chain Management, użytkownik usługi Field Service może zaktualizować zamówienie zakupu tylko wtedy, gdy stan zatwierdzenia w aplikacji Supply Chain Management ma stan *Wersja robocza*.
- Kilka kolumn jest zarządzanych tylko przez Supply Chain Management i nie można ich zaktualizować w usłudze Field Service. Aby dowiedzieć się, których kolumn nie można zaktualizować, przejrzyj tabele mapowania w produkcie. Aby zachować prostotę rozwiązania, większość z tych kolumn jest ustawiona jako tylko do odczytu na stronach usługi Dataverse. 

    Na przykład kolumnami informacji o cenach zarządza aplikacja Supply Chain Management. W aplikacji Supply Chain Management są zawarte umowy handlowe, z których zalet może korzystać usługa Field Service. Kolumny takie jak **Cena jednostkowa**, **Rabat** i **Kwota netto** pochodzą tylko z aplikacji Supply Chain Management. Aby mieć pewność, że cena jest synchronizowana z usługą Field Service, po wprowadzeniu danych zamówienia zakupu należy użyć funkcji **Synchronizuj** na stronach **Zamówienie zakupu** i **Produkt zamówienia zakupu** w usłudze Dataverse. Aby uzyskać więcej informacji, zobacz temat [Synchronizowanie z danymi zaopatrzenia aplikacji Dynamics 365 Supply Chain Management na żądanie](#sync-procurement).

- Kolumna **Sumy** jest dostępna tylko w usłudze Field Service, ponieważ w aplikacji Supply Chain Management nie ma aktualnych sum zamówienia zakupu. Sumy w aplikacji Supply Chain Management są obliczane na podstawie wielu parametrów, które nie są dostępne w usłudze Field Service.
- Wiersze zamówienia zakupu, w których określono tylko kategorię zaopatrzenia lub jeśli określony produkt ma typ *Usługa* lub jest produktem usługi Field Service, można zainicjować tylko w aplikacji Supply Chain Management. Wiersze są następnie synchronizowane do usługi Dataverse i widoczne w usłudze Field Service.
- Jeśli zainstalowano tylko usługę Field Service, a aplikację Supply Chain Management nie, kolumna **Magazyn** jest obowiązkowa w zamówieniu zakupu. Jednak jeśli zostanie zainstalowana aplikacja Supply Chain Management, wymaganie to zostanie zweryfikowane, ponieważ Supply Chain Managementu możliwia tworzenie wierszy zamówień zakupu, w których nie określono magazynu w pewnych sytuacjach.
- Przyjęcia produktów (przyjęcia zamówień zakupu w usłudze Dataverse) są zarządzane przez Supply Chain Management i nie można ich utworzyć z poziomu usługi Dataverse, jeśli zainstalowano aplikację Supply Chain Management. Przyjęcia produktów z Supply Chain Management są synchronizowane z aplikacji Supply Chain Management do usługi Dataverse.
- Niedobór w dostawie jest dozwolony w aplikacji Supply Chain Management. Rozwiązanie OneFSSCM dodaje logikę, dzięki której podczas tworzenia lub aktualizowania wiersza dokumentu przyjęcia produktów (lub przyjęcia produktu w zamówieniu zakupu w usłudze Dataverse) tworzony jest wiersz arkusza magazynowego w celu skorygowania pozostałej ilości, która jest na zamówieniu w scenariuszach niedoboru w dostawie w usłudze Dataverse.

## <a name="unsupported-scenarios"></a>Nieobsługiwane scenariusze

- Usługa Field Service uniemożliwia dodanie wierszy do anulowanych zamówień zakupu w aplikacji Supply Chain Management. W celu obejścia tego problemu można na przykład zmienić stan systemowy zamówienia zakupu w usłudze Field Service, a następnie dodać nowy wiersz w aplikacji Field Service lub Supply Chain Management.
- Chociaż wiersze zaopatrzenia wpływają na poziomy zapasów w obu systemach, nie zapewnia to dopasowania zapasów między usługami Supply Chain Management i Field Service. Aplikacje Field Service i Supply Chain Management mają inne procesy, które aktualizują poziomy zapasów. Te procesy są poza zakresem zaopatrzenia.

## <a name="status-management"></a>Zarządzanie stanem

Stany zamówień zakupu w usłudze Field Service różnią się od stanów w aplikacji Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Stany produktów w zamówieniu zakupu i zamówień zakupu w usłudze Field Service

| Nagłówek — stan systemowy | Nagłówek — stan zatwierdzenia | Stan pozycji |
|---|---|---|
| <ul><li>Robocza</li><li>Przesłany</li><li>Anulowane</li><li>Produkt przyjęty</li><li>Zafakturowane</li></ul> | <ul><li>Null</li><li>Zatwierdzone</li><li>Odrzucona</li></ul> | <ul><li>Oczekująca</li><li>Odebrane</li><li>Anulowane</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Stany zamówienia zakupu i wiersza zamówienia zakupu w aplikacji Supply Chain Management

Stany zatwierdzenia wiersza są aktywne tylko wtedy, gdy istnieje przepływ pracy wiersza.

| Nagłówek — stan dokumentów | Nagłówek — stan zatwierdzenia | Stan wiersza | Stan zatwierdzenia wiersza |
|---|---|---|---|
| <ul><li>Zamówienie otwarte (zamówienie zaległe)</li><li>Odebrane</li><li>Zafakturowany</li><li>Anulowane</li></ul> | <ul><li>Robocza</li><li>W trakcie przeglądu</li><li>Zatwierdzone</li><li>Odrzucona</li><li>W trakcie przeglądu zewnętrznego</li><li>Potwierdzone</li><li>Zakończone</li></ul> | <ul><li>Zamówienie otwarte (zamówienie zaległe)</li><li>Odebrane</li><li>Zafakturowany</li><li>Anulowane</li></ul> | <ul><li>Nieprzesłane</li><li>W trakcie przeglądu</li><li>Zatwierdzone</li><li>Odrzucona</li></ul> |

Do kolumn stanu stosowane są następujące reguły:

- Nie można zaktualizować stanu w aplikacji Supply Chain Management z poziomu usługi Field Service. Jednak w niektórych przypadkach stan w usłudze Field Service zostanie zaktualizowany w momencie zmiany stanu zamówienia zakupu w aplikacji Supply Chain Management.
- Jeśli zamówienie zakupu w Supply Chain Management podlega zarządzaniu zmianami i zmiana jest przetwarzana, stan zatwierdzenia to *Wersja robocza* lub *W trakcie przeglądu*. W takim przypadku stan zatwierdzenia usługi Field Service zostanie ustawiony na wartość *Null*.
- Jeśli stan zatwierdzenia zamówienia zakupu w aplikacji Supply Chain Management jest ustawiony na *Zatwierdzone*, *W trakcie przeglądu zewnętrznego*, *Potwierdzone* lub *Zakończone*, stan zatwierdzenia zamówienia zakupu w usłudze Field Service zostanie ustawiony na *Zatwierdzone*.
- Jeśli stan zatwierdzenia zamówienia zakupu w aplikacji Supply Chain Management jest ustawiony na *Odrzucone*, stan zatwierdzenia zamówienia zakupu w usłudze Field Service zostanie ustawiony na *Odrzucone*.
- Jeśli stan nagłówka dokumentu w aplikacji Supply Chain Management zostanie zmieniony na *Zamówienie otwarte (zamówienie zaległe)*, a stan zamówienia zakupu Field Service to *Wersja robocza* lub *Anulowane*, stan zamówienia zakupu w usłudze Field Service zostanie zmieniony na *Przesłane*.
- Jeśli stan nagłówka dokumentu w aplikacji Supply Chain Management zostanie zmieniony na *Anulowane*, a w usłudze Field Service z zamówieniem zakupu nie są skojarzone żadne produkty przyjęcia zamówienia zakupu (za pośrednictwem produktów zamówienia zakupu), stan systemowy usługi Field Service jest ustawiany na *Anulowane*.
- Jeśli stan wiersza zamówienia zakupu w aplikacji Supply Chain Management to *Anulowano*, stan produktu zamówienia zakupu w usłudze Field Service jest ustawiany na *Anulowane*. Ponadto jeśli stan wiersza zamówienia zakupu w aplikacji Supply Chain Management zostanie zmieniony z *Anulowane* na *Zamówienie zaległe*, stan pozycji produktu zamówienia zakupu w usłudze Field Service zostanie ustawiony na *Oczekujące*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Synchronizowanie danych zaopatrzenia w aplikacji Supply Chain Management na żądanie

Supply Chain Management obejmuje dane dotyczące zaopatrzenia, które obsługują umowy handlowe, rabaty i inne scenariusze oparte na procesach drugorzędnych w aplikacji Supply Chain Management. Aparat zaopatrzenia używa złożonych reguł w celu określenia najlepszej ceny dla danego zamówienia zakupu. W przypadku korzystania z funkcji podwójnego zapisu dane nie zawsze są przechowywane synchronicznie w obu środowiskach, zwłaszcza w scenariuszach, w których wiersz został utworzony lub zaktualizowany na podstawie usługi Dataverse, i mogą wyzwalać kolejne procesy w aplikacji Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Synchronizowanie danych zaopatrzenia na podstawie aplikacji Supply Chain Management

1. W usłudze Dataverse przejdź do pozycji **Zapasy \> Zamówienie zakupu**.
2. Wybierz **Nowy**, aby utworzyć nowe zamówienie zakupu, lub wybierz wiersz dla istniejącego zamówienia zakupu.
3. Na podstawie zamówienia zakupu lub wiersza zamówienia zakupu.
4. W okienku akcji wybierz pozycję **Synchronizuj**.

Wszystkie kolumny z usługi Dataverse i Field Service udostępnione w usłudze Supply Chain Management są synchronizowane.

Poniżej przedstawiono sytuacje, w których można korzystać z funkcji **synchronizacji**:

- W przypadku wielokrotnego sukcesywnego zmieniania tego samego wiersza w usłudze Dataverse należy uruchomić funkcję **Synchronizuj**.
- Jeśli nie masz pewności, czy zmiana może stanowić drugą sukcesywną zmianę w usłudze Dataverse, uruchomienie funkcji **Synchronizuj** może mieć sens.
- Jeśli zostanie wyświetlony komunikat o błędzie aktualizacji wartości z aplikacji Supply Chain Management, należy uruchomić funkcję **synchronizacji**, a następnie ponowić próbę aktualizacji w programie Dataverse.

## <a name="cancelling-the-posting-process"></a>Anulowanie procesu księgowania

Jeśli proces księgowania dokumentu przyjęcia produktów został anulowany podczas przetwarzania, system podwójnego zapisu może utworzyć wiersz dokumentu przyjęcia produktów w tym wierszu w usłudze Dataverse, ale nie może utworzyć wiersza dokumentu przyjęcia produktów w aplikacji Supply Chain Management. Taka sytuacja ma miejsce, ponieważ podwójny zapis nie obsługuje transakcji rozproszonych.

## <a name="templates"></a>Szablony

Do integracji dokumentów związanych z zaopatrzeniem służą następujące szablony.

| Zarządzanie łańcuchem dostaw | Field Service | opis |
|---|---|---|
| [Nagłówek zamówienia zakupu (wersja 2)](mapping-reference.md#183) | msdyn\_Purchaseorders | Ta tabela zawiera kolumny reprezentujące nagłówek zamówienia zakupu. |
| [Jednostka wiersza zamówienia zakupu](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | Ta tabela zawiera wiersze reprezentujące wiersze w zamówieniu zakupu. Numer produktu jest używany podczas synchronizacji. Identyfikuje produkt jako jednostkę magazynową (SKU), w tym wymiary produktu. Aby uzyskać więcej informacji na temat integracji produktów z usługą Dataverse, zobacz temat [Ujednolicone działanie produktu](product-mapping.md). |
| [Nagłówek dokumentu przyjęcia produktów](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | Ta tabela zawiera nagłówki dokumentów przyjęcia produktów, które są tworzone po zaksięgowaniu dokumentu przyjęcia produktów w aplikacji Supply Chain Management. |
| [Wiersz dokumentu przyjęcia produktów](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | Ta tabela zawiera wiersze dokumentów przyjęcia produktów, które są tworzone po zaksięgowaniu dokumentu przyjęcia produktów w aplikacji Supply Chain Management. |
| [Jednostka usuniętego nietrwale wiersza zamówienia zakupu](mapping-reference.md#182) | msdyn\_purchaseorderproducts | Ta tabela zawiera informacje o wierszach zamówienia zakupu, które są usuwane nietrwale. Wiersz zamówienia zakupu w aplikacji Supply Chain Management można usunąć nietrwale tylko wtedy, gdy zamówienie zakupu zostało potwierdzone lub zatwierdzone w przypadku włączenia zarządzania zmianami. Wiersz istnieje w bazie danych Supply Chain Management i jest oznaczony jako **IsDeleted**. Ponieważ usługa Dataverse nie ma koncepcji usuwania nietrwałego, bardzo ważne jest, aby te informacje zostały zsynchronizowane z usługą Dataverse. W ten sposób wiersze, które są usuwane nietrwale w aplikacji Supply Chain Management, mogą być automatycznie usuwane z usługi Dataverse. W tym przypadku logika usuwania wiersza w usłudze Dataverse jest zlokalizowana w rozszerzonej aplikacji Supply Chain Management. |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
