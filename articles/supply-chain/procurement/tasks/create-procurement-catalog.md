---
title: Tworzenie katalogu zaopatrzenia
description: W tym temacie wyjaśniono, jak utworzyć katalog zaopatrzenia.
author: RichardLuan
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaf8b8d8b369aa704344d6984a0f111af6e4285b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016484"
---
# <a name="create-a-procurement-catalog"></a>Tworzenie katalogu zaopatrzenia

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak utworzyć katalog zaopatrzenia. To zadanie jest zazwyczaj wykonywane przez pracownika działu zaopatrzenia. Dowiedz się także, jak pracownicy mogą używać katalogu podczas tworzenia zapotrzebowania. Aby można było utworzyć katalogu, w systemie musi istnieć hierarchia kategorii zaopatrzenia. Hierarchia, wraz ze wszystkimi znajdującymi się w niej produktami, jest dziedziczona przez nowy katalog. Można użyć tego przewodnika z danymi firmy demonstracyjne USMF, gdzie hierarchia kategorii zaopatrzenia jest już dostępna, oraz wobec przykładów opisanych w krokach procedury.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Sprawdzanie, czy istnieje hierarchia kategorii zaopatrzenia
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Kategorie zaopatrzenia**. W danych firmy demonstracyjnej USMF jest dostępna hierarchia kategorii zaopatrzenia, a produkty zostały dodane do kategorii **Urządzenia biurowe/Komputery**. Jeśli wykonujesz tę procedurę jako przewodnik po zadaniu, musisz odblokować przewodnik, aby móc przeglądać kategorię. Jeśli hierarchia nie była dostępna, należało ją utworzyć klikając przycisk **Nowa**. Można to zrobić tylko raz.  
2. Zamknij stronę.

## <a name="create-a-catalog"></a>Tworzenie katalogu
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Katalogi > Katalogi zaopatrzenia**.
2. Wybierz **Nowy katalog zaopatrzenia**, aby otworzyć rozwijane okno dialogowe.
3. W polu **Nazwa** wpisz wartość.
4. Kliknij przycisk **OK**.
5. W drzewie rozwiń węzeł **KATEGORIE ZAOPATRZENIA W FIRMIE**.
6. W drzewie rozwiń węzeł **URZĄDZENIA BIUROWE**.
7. W drzewie zaznacz pozycję **Komputery**.

  - Produkty z kategorii zaopatrzenia są wyświetlane na liście. Jeśli chcesz dodać produkt do kategorii, trzeba to zrobić na stronie **Hierarchia kategorii zaopatrzenia** lub na stronie **Szczegóły pozycji**.  
  - **Domyślny** typ aktualizacji określa, czy nowe produkty dodawane do hierarchii kategorii zaopatrzenia są natychmiast widoczne w katalogu. Jeśli jako typ aktualizacji ustawiono wartość **Dynamiczne**, zmiany są widoczne natychmiast. Jeśli typem aktualizacji jest **Statyczne**, nowe produkty są widoczne tylko dla osób używających katalogu po jego ponownym opublikowaniu. Akcja **Publikuj** jest dostępna w okienku akcji u góry strony. Jeśli produkty zostaną usunięte z hierarchii kategorii zaopatrzenia, zmiana jest natychmiast widoczna, niezależnie od wartości w polu **Domyślny** typ aktualizacji.  

8. W okienku akcji wybierz pozycję **Kategoria nawigacji** i upewnij się, że wybrano opcję **Włączone**.
9. Wybierz **Uaktywnij katalog**.
10. Zamknij stronę.

## <a name="make-the-catalog-visible"></a>Ustawianie widoczności katalogu
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Ustawienia > Zasady > Zasady zakupów**.
2. Wybierz zasadę **Procurement Policy USMF**. Należy wybrać zasady zakupów dla firmy, w której pracownik połączony z Twoim profilem użytkownika może zamawiać produkty. W danych firmy demonstracyjnej USMF administrator jest połączony z pracownikiem **Julia Funderburk**. Julia domyślnie zamawia produkty w USMF.  
3. Zaznacz nowo utworzony katalog.
4. Kliknij przycisk **OK**.

## <a name="use-the-catalog"></a>Używanie katalogu
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Wszystkie zapotrzebowania na zakup**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wpisz wartość.
4. Kliknij przycisk **OK**.
5. Wybierz pozycję **Dodaj produkty**.
6. Na liście znajdź i zaznacz odpowiedni rekord. Do filtrowania produktów można używać hierarchii kategorii po lewej stronie lub filtru u góry listy.  
7. Wybierz pozycję **Dodaj do wierszy**.
8. Kliknij przycisk **OK**.

