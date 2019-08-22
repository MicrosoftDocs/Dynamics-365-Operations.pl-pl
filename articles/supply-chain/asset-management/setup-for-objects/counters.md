---
title: Pomiary składnika majątku
description: W tym temacie wyjaśniono, jak tworzyć typy pomiarów składników majątku w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783525"
---
# <a name="asset-measures"></a>Pomiary składnika majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak tworzyć typy pomiarów składników majątku w Zarządzaniu składnikami majątku. Typy miar składników majątku służą do rejestracji miar składników majątku, np. liczby godzin produkcji lub ilości wyprodukowanej w ramach składnika majątku. Typy składników majątku są powiązane z typami miar składników majątku. Oznacza to, że miara składnika majątku może być używana tylko w przypadku, kiedy miara składnika majątku jest ustawiona jako typ składnika majątku używany względem składnika majątku.

Zanim zarejestrujesz miarę składników majątku, najpierw utwórz typy składników majątku, których chcesz używać w **Licznikach**. Następnie można utworzyć rejestracje pomiarów składników majątku w sekcji **Pomiary składnika majątku**. 

Pomiary składnika majątku powinny być używane w planach konserwacji. Wiersz planu konserwacji powinien mieć typ „Licznik”, na przykład powinien odnosić się do godzin produkcji lub ilości wyprodukowanego towaru. 

Rejestrację miary składnika aktywów można zaktualizować ręcznie lub automatycznie na podstawie godzin produkcyjnych lub produkowanych ilości. Miara środka trwałego może być ustawiona tak , aby korzystała z jednej z trzech metod aktualizacji (wybranych w polu **Aktualizacja** w **licznikach**):
  
- Ręcznie — należy ręcznie zarejestrować wartości pomiarów środków trwałych.  
- Godziny produkcji - licznik jest automatycznie aktualizowany na podstawie liczby godzin produkcyjnych.  
- Ilość produkcji - licznik jest automatycznie aktualizowany na podstawie ilości wyprodukowanego towaru.  

>[!NOTE]
>W przypadku użycia wyprodukowanej ilości *wszystkie* zarejestrowane pozycje są uwzględniane w rejestracji pomiarów, ilości dobrych, a także ilości błędów. W razie potrzeby zawsze możliwe jest ręczne rejestrowanie miar składników majątku.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Tworzenie typów liczników dla rejestracji liczników składników majątku

1. Wybierz **Zarządzaj składnikiem majątku** > **Konfiguracja** > **Typy składników majątku** > **Liczniki**.
2. Wybierz pozycję **Nowy**, aby utworzyć typ miary składnika majątku.
3. Wstaw Identyfikator w polu **Licznik** oraz nazwę licznika w polu **Nazwa**.
4. Na skróconej karcie **Ogólne** wybierz jednostkę miary w polu **jednostka.**
5. W polu **aktualizacja** wybierz metodę aktualizacji stosowaną dla miary składnika majątku.
6. Zaznacz opcję „tak” na przycisku przełącznika **Dziedzicz wartości licznika**, jeśli zasoby podrzędne w strukturze zasobów powinny automatycznie dziedziczyć rejestracje miar składnika majątku dokonane w zasobie nadrzędnym.
7. W polu **Zagregowana suma** wybierz metodę sumowania stosowaną dla miary składnika majątku przy użyciu tego typu miary składnika majątku. „Suma” to standardowy wybór używany do ciągłego dodawania zarejestrowanych wartości do wartości całkowitej. „Średnia” może być użyta, jeśli miara składnika majątku jest ustawiona pod kątem monitorowania progu, na przykład w odniesieniu do temperatury, drgań lub zużycia danego składnika majątku. 
8. W polu **odchylenie nad** wstaw górny poziom w procentach, aby sprawdzić poprawność, jeśli ręczne rejestrowanie miar składników majątku znajduje się w oczekiwanym zakresie. Sprawdzanie poprawności jest oparte na liniowym wzroście istniejących rejestracji miar składnika majątku.
9. W polu **odchylenie pod** wstaw dolny poziom w procentach, aby sprawdzić poprawność, jeśli ręczne rejestrowanie miar składników majątku znajduje się w oczekiwanym zakresie. Sprawdzanie poprawności jest oparte na liniowym spadku istniejących rejestracji miar składnika majątku.
10. W polu **typ** wybierz typ wiadomości (informacje, ostrzeżenie, błąd), które mają być wyświetlane, jeśli odchylenia poza zdefiniowanym zakresem wystąpią podczas ręcznego rejestrowania miar składników majątku.
11. Na skróconej karcie **Typy składników majątku** dodaj typy składników majątku, dla których ma być stosowana miara składnika majątku.
12. Na skróconej karcie **Powiązane pomiary składnika majątku** dodaj miary składnika majątku, które mają być automatycznie aktualizowane po zaktualizowaniu tej miary składnika majątku.


>[!NOTE]
>Powiązane pomiary składnika majątku są automatycznie aktualizowane tylko wtedy, gdy miara składnika majątku ma typ składnika majątku, z którym jest powiązana w ustawieniach miary składnika majątku. Na przykład: możesz skonfigurować miarę składnika majątku dla godzin produkcji i dodać typ składnika „silnik do samochodu ciężarowego”. Po zaktualizowaniu tego składnika majątku powiązany licznik „Olej” jest również aktualizowany o te same wartości składnika majątku. Konfiguracja w **licznikach** zawiera ustawienia „godziny”. Ponadto w pomiarze składnika majątku „Olej” na skróconej karcie **typy składnika majątku** należy dodać „Silnik do samochodu ciężarowego”, aby ustanowić relację pomiaru składnika majątku. Zobacz poniższe zrzuty ekranu, aby zapoznać się z przykładowymi ustawieniami dla Godzin i pomiarów składnika majątku „Olej”.

Gdy typy składników majątku zostaną dodane do typu pomiaru składnika majątku w części **Liczniki**, te miary składnika majątku są automatycznie dodawane do typów składnika majątku na skróconej karcie **Liczniki** w [Typy składników majątku](../setup-for-objects/object-types.md).

![Rysunek 1](media/071-setup-for-objects.png)


