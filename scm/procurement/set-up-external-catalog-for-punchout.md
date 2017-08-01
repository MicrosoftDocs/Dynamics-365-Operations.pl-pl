---
title: "Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut eProcurement"
description: "W tym temacie opisano używanie zewnętrznego katalogu (dynamicznie dostępnego katalogu dostawcy, punchout) w celu zbierania informacji ofertowych od dostawcy i dodawania ich do zapotrzebowania."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 2d853cb963471f81d7a2a09a0f7913722de8a417
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# <a name="set-up-an-external-catalog-for-punchout-eprocurement"></a>Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut eProcurement

Używając zewnętrznego katalogu, można mieć pewność, że informacje o produktach i cenach, które następnie będą przetwarzane w programie Dynamics 365 for Finance and Operations Enterprise Edition w wersji z lipca 2017 roku, są dokładne i aktualne. Zapotrzebowanie można następnie zatwierdzić i przekonwertować na zamówienie zakupu, które zostanie złożone u dostawcy.

Po skonfigurowaniu zewnętrznego katalogu pracownik przygotowujący zapotrzebowanie będzie miał możliwość przejścia do zewnętrznej witryny (zewnętrznego katalogu), a następnie zwrócenia z niej koszyka zakupów do swojej macierzystej witryny. Ta komunikacja opiera się na protokole cXML i musi być skonfigurowana między systemami organizacji kupującej i sprzedającej.

Aby można było skonfigurować taką komunikację, dostawca musi podać elementy informacji, których będziesz używać w konfiguracji zewnętrznego katalogu, takie jak tożsamość, domena firmy nabywcy (na przykład „DUNS” i „Numer DUNS”), poświadczenia oraz adres URL, pod którym jest dostępny katalog dostawcy.

## <a name="setting-up-an-external-catalog"></a>Konfigurowanie zewnętrznego katalogu

Zewnętrzny katalog powinien umożliwiać pracownikowi wprowadzającemu zapotrzebowanie na zakup przejście do zewnętrznej witryny w celu wybrania produktów. Produkty wybrane przez pracownika z zewnętrznego katalogu są zwracane do programu Dynamics 365 for Finance and Operations z aktualnymi informacjami cenowymi i z tego miejsca mogą zostać dodane do zapotrzebowania na zakup. Celem nie jest umożliwienie pracownikom składania zamówień bezpośrednio w zewnętrznej witrynie. Podczas konfigurowania zewnętrznego katalogu należy upewnić się, że celem witryny dostępnej przez zewnętrzny katalog jest tylko zebranie informacji ofertowych, a nie złożenie faktycznego zamówienia.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Aby skonfigurować zewnętrzny katalog dostawcy, należy wykonać następujące zadania:

1. Ustawianie hierarchii kategorii zaopatrzenia. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia](/https://ax.help.dynamics.com/en/wiki/set-up-policies-for-procurement-category-hierarchies/).
2. Zarejestrowanie dostawcy w programie Finance and Operations. Aby można było utworzyć konfiguracje pozwalające na dostęp do zewnętrznego katalogu dostawcy, należy skonfigurować dostawcę i jego osobę kontaktową w programie Microsoft Dynamics 365. Ponadto dostawca zewnętrznego katalogu musi być dodany do wybranej kategorii zaopatrzenia. Aby uzyskać więcej informacji o rejestrowaniu dostawców w programie Microsoft Dynamics 365, zobacz [Zarządzanie użytkownikami modułu Współpraca z dostawcami](/procurement/manage-vendor-collaboration-users.md). Aby uzyskać informacje o przypisywaniu dostawcy do kategorii zaopatrzenia, zobacz [Zatwierdzanie dostawców dla konkretnych kategorii zaopatrzenia](/https://ax.help.dynamics.com/en/wiki/approve-vendors-for-specific-procurement-categories/).
3. Skonfigurowanie jednostek miary i waluty używanych przez dostawcę. Aby uzyskać informacje o tworzeniu jednostki miary, zobacz [Tworzenie jednostek miary](/https://ax.help.dynamics.com/en/wiki/manage-unit-of-measure/).
4. Skonfigurowanie zewnętrznego katalogu dostawcy z uwzględnieniem wymagań obowiązujących w witrynie tego katalogu. Więcej informacji o tym zadaniu znajdziesz w następnej części.
5. Przetestowanie konfiguracji zewnętrznego katalogu dostawcy w celu sprawdzenia, czy ustawienia są prawidłowe i czy masz dostęp do katalog. Za pomocą akcji **Sprawdź poprawność ustawień** zweryfikuj zdefiniowany przez siebie komunikat konfiguracji żądania. Ten komunikat powinien powodować otwieranie witryny zewnętrznego katalogu dostawcy w oknie przeglądarki internetowej. Podczas sprawdzania poprawności nie można zamawiać towarów ani usług od dostawcy. Aby zamawiać towary i usługi, należy przejść do katalogu dostawcy z poziomu zapotrzebowania na zakup.
6. Aktywacja zewnętrznego katalogu za pomocą przycisku **Uaktywnij katalog** znajdującego się na stronie **Katalogi zewnętrzne**. Zewnętrzny katalog musi zostać aktywowany, zanim będą go mogli używać pracownicy. Zewnętrzny katalog można w dowolnym momencie zdezaktywować.


## <a name="4-configure-the-external-vendor-catalog"></a>(4) Konfigurowanie zewnętrznego katalogu dostawcy

W tej sekcji dokładniej omówiono 4 zadania z poprzedniej części.

1. Wprowadź nazwę i opis katalogu zewnętrznego dostawcy. Wprowadzona nazwa pojawi się w koszyku reprezentującym zewnętrzny katalog, który będzie wyświetlany pracownikom tworzącym zapotrzebowania. Pracownicy mogą kliknąć koszyk, a zostanie otwarty katalog w witrynie zewnętrznego katalogu dostawcy.
2. Dodaj obraz przy użyciu akcji **Obraz z katalogu zewnętrznego**. Obraz pojawi się w koszyku reprezentującym zewnętrzny katalog, który będzie wyświetlany pracownikom tworzącym zapotrzebowania. Należy zwrócić uwagę, że szerokość i wysokość obrazu muszą być takie same. W przeciwnym razie obraz nie będzie wyświetlany poprawnie.
3. Określ, czy witryna sieci Web zewnętrznego katalogu dostawcy ma być wyświetlana w tym samym oknie przeglądarki, w którym pracownik utworzył zapotrzebowanie, czy też w nowym oknie.
4. Wybierz dostawcę dla katalogu. Na liście **Firmy** jest wiersz dla każdej firmy, w której skonfigurowano dostawcę. Aby zezwolić użytkownikom na wnioskowanie o produkty bezpośrednio z katalogu dostawcy w niektórych firmach, a w innych nie, można użyć przycisku **Zabroń dostępu** lub **Zezwalaj na dostęp** dla każdej firmy, w której katalog ma być dostępny lub nie.
5. W polu **Domyślne wygaśnięcie (dni)** wprowadź liczbę dni, przez jaką oferta otrzymana z zewnętrznego katalogu jest ważna i może być używana do kupowania od zewnętrznego dostawcy. Po utworzeniu oferty i pobraniu jej z witryny zewnętrznego katalogu dostawcy oferta jest ważna na dzień określony bieżącą datą systemową i pozostaje ważna przez liczbę dni wprowadzoną w tym polu.
6. Kliknij przycisk **Dodaj**, aby rozpocząć mapowanie kategorii zaopatrzenia na zewnętrzny katalog. Następnie na liście Nazwa kategorii wybierz kategorię. Lista kategorii jest podzbiorem kategorii zaopatrzenia, do których zamapowano dostawcę we wszystkich firmach skonfigurowanych dla tego dostawcy.
[!NOTE]
Zasady zaopatrzenia są używane w celu zezwolenia na dostęp lub ograniczenia dostępu do kategorii dla kupującej firmy lub przyjmującej jednostki operacyjnej. Możliwość wybierania z zewnętrznego katalogu wymaga zezwolenia na dostęp do co najmniej jednej kategorii zaopatrzenia zamapowanej do katalogu.
7. Skonfiguruj komunikat żądania konfiguracji cXML, który będzie wysyłany dostawcy. Format automatycznie generowanego komunikatu jest minimalnym szablonem wymaganym do rozpoczęcia sesji. Wprowadź wartości znaczników.

W dowolnym momencie można ponownie załadować systemowy szablon komunikatu, klikając przycisk **Przywróć format komunikatu**. Należy zauważyć, że jeśli przywrócisz format komunikatu, bieżący komunikat zostanie zastąpiony przez automatycznie wygenerowany format komunikatu, który ma puste znaczniki.

### <a name="cxml-setup-message"></a>Komunikat konfiguracyjny cXML
Poniżej znajduje się opis znaczników zawartych w szablonie:

| Pole | opis | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|Domena firmy nabywcy.|
|< Header >< From >< Credential>< Identity >< /Identity > | Tożsamość firmy nabywcy.|
|< Header >< To >< Credential domain=”” > | Domena firmy dostawcy.|
|< Header >< To >< Credential>< Identity >< /Identity> | Tożsamość firmy dostawcy.|
|< Header >< Sender >< Credential domain=”” > | Domena firmy nabywcy.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | Tożsamość firmy nabywcy.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|Wspólny klucz tajny firmy nabywcy.|
|< Request deploymentMode=”” >|Środowisko testowe lub produkcyjne.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|Adres URL punktu końcowego z zewnętrznym katalogiem dostawcy.|

### <a name="extrinsic-elements"></a>Elementy zewnętrzne

Element zewnętrzny to dodatkowe informacje, takie jak nazwa użytkownika, które zależy od użytkownika dokonującego wyboru w zewnętrznym katalogu. Element zewnętrzny jest ustawiany podczas wybierania w zewnętrznym katalogu i może być wysyłany w komunikacie żądania konfiguracji.
Dostawca może ustanowić wymóg, aby w żądaniu konfiguracji był mu przesyłany element zewnętrzny. W takim przypadku należy dodać element zewnętrzny do listy elementów zewnętrznych na stronie **Katalog zewnętrzny** w sekcji **Format komunikatu**. Nadaj elementowi zewnętrznemu nazwę, którą dostawca może rozpoznać, i zamapuj ją na wartość. Dostępne opcje wartości: Nazwa użytkownika, Adres e-mail użytkownika lub Wartość losowa.
Aby uzyskać więcej informacji o protokole cXML, zobacz: http://cxml.org/

## <a name="post-back-message"></a>Komunikat ogłaszania zwrotnego
Komunikat ogłaszania zwrotnego to komunikat otrzymywany od dostawcy, gdy użytkownik finalizuje transakcję w zewnętrznej witrynie i wraca do programu Finance and Operations. Komunikatów ogłaszania zwrotnego nie można konfigurować. Komunikat bazuje na definicji protokołu cXML. Poniżej przedstawiono informacje, które mogą wchodzić w skład komunikatu ogłaszania zwrotnego otrzymywanego w wierszu zapotrzebowania:

| Komunikat otrzymywany od dostawcy | Informacja kopiowana do wiersza zapotrzebowania w programie Finance and Operations|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Ilość|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|Identyfikator zewnętrznego towaru|
|< ItemDetail>< UnitPrice >< Money currency=”” >| Waluta|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Cena jednostkowa|
|< ItemDetail >< Description ShortName=”” >|Nazwa produktu|
|< ItemDetail >< Description >< /Description >|Zawarty w opisie towaru; Nazwa produktu, jeśli atrybut ShortName nie jest określony.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Jednostka|
|< ItemDetail >< Classification >< /Classification >|Zawarty w opisie towaru|
|< ItemDetail >< Classification domain=”” >|Zawarty w opisie towaru|

## <a name="delete-an-external-catalog"></a>Usuwanie katalogu zewnętrznego
Katalog zewnętrzny można usunąć za pomocą operacji Usuń dostępnej na stronie.

Jeśli poproszono o produkt z zewnętrznego katalogu dostawcy, nie można usunąć tego katalogu. Zamiast tego dla katalogu jest ustawiany stan nieaktywności. Jeśli chcesz usunąć dostęp do witryny z zewnętrznym katalogiem dostawcy, ale bez usuwania samego katalogu, zmień stan zewnętrznego katalogu na Nieaktywny.


