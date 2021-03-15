---
title: Pomiary składnika majątku
description: W tym temacie wyjaśniono, jak tworzyć typy pomiarów składników majątku w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 37f47b3d9ba0344b96db5626359e2a99a1a40f9c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018528"
---
# <a name="counters"></a>Liczniki

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak tworzyć typy liczników w module Zarządzanie składnikami majątku. Typy liczników służą do rejestracji liczników składników majątku, np. liczby godzin produkcji lub ilości wyprodukowanej w ramach składnika majątku. Typy składników majątku są powiązane z typami liczników. Oznacza to, że licznik może być używany tylko w przypadku, gdy licznik jest ustawiony jako typ składnika majątku używany względem składnika majątku.

Zanim zarejestrujesz liczniki dla składników majątku, najpierw utwórz typy liczników, których chcesz używać w obszarze **Liczniki**. Następnie można utworzyć rejestracje liczników składników majątku w sekcji **Liczniki**. 

Liczniki powinny być używane w planach konserwacji. Wiersz planu konserwacji powinien mieć typ „Licznik”, na przykład powinien odnosić się do godzin produkcji lub ilości wyprodukowanego towaru. 

Rejestrację licznika można zaktualizować ręcznie lub automatycznie na podstawie godzin produkcyjnych lub produkowanych ilości. Licznik można ustawić tak, aby korzystał z jednej z trzech metod aktualizacji (wybranych w polu **Aktualizacja** w obszarze **Liczniki**):
  
- Ręcznie — należy ręcznie zarejestrować wartości liczników.  
- Godziny produkcji - licznik jest automatycznie aktualizowany na podstawie liczby godzin produkcyjnych.  
- Ilość produkcji - licznik jest automatycznie aktualizowany na podstawie ilości wyprodukowanego towaru.  

>[!NOTE]
>W przypadku użycia wyprodukowanej ilości *wszystkie* zarejestrowane pozycje są uwzględniane w rejestracji liczników, ilości dobrych, a także ilości wadliwych towarów. W razie potrzeby zawsze można zarejestrować liczniki ręcznie.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Tworzenie typów liczników dla rejestracji liczników składników majątku

1. Wybierz **Zarządzaj składnikiem majątku** > **Konfiguracja** > **Typy składników majątku** > **Liczniki**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy typ licznika.
3. Wstaw Identyfikator w polu **Licznik** oraz nazwę licznika w polu **Nazwa**.
4. Na skróconej karcie **Ogólne** wybierz jednostkę licznika w polu **Jednostka**.
5. W polu **Aktualizacja** wybierz metodę aktualizacji stosowaną dla licznika.
6. Wybierz pozycję „Tak” na przycisku przełącznika **Dziedzicz wartości licznika**, jeśli podrzędne składniki majątku w strukturze składników majątku powinny automatycznie dziedziczyć rejestracje liczników dokonane w nadrzędnym składniku majątku.
7. W polu **Zagregowana suma** wybierz metodę sumowania stosowaną dla licznika przy użyciu tego typu licznika. „Suma” to standardowy wybór używany do ciągłego dodawania zarejestrowanych wartości do wartości całkowitej. „Średnia” może być używana, jeśli licznik zostanie skonfigurowany do monitorowania progu, na przykład w odniesieniu do temperatury, drgań lub zużycia danego składnika majątku. 
8. W polu **Odchylenie powyżej** wstaw górny poziom w procentach, aby sprawdzić poprawność, jeśli ręczne rejestracje znajdują się w oczekiwanym zakresie. Weryfikacja opiera się na liniowym wzroście istniejących rejestracji liczników.
9. W polu **Odchylenie poniżej** wstaw dolny poziom w procentach, aby sprawdzić, czy ręczne rejestracje znajdują się w oczekiwanym zakresie. Weryfikacja opiera się na liniowym spadku istniejących rejestracji liczników.
10. W polu **Typ** wybierz typ komunikatu (informacje, ostrzeżenie, błąd), który mają być wyświetlana, jeśli odchylenia poza zdefiniowanym zakresem wystąpią podczas ręcznego rejestrowania liczników.
11. Na skróconej karcie **Typy składników majątku** dodaj typy składników majątku, dla których ma być stosowany licznik.
12. Na skróconej karcie **Powiązane liczniki składnika majątku** dodaj licznik, który mają być automatycznie aktualizowany po zaktualizowaniu tego licznika.


>[!NOTE]
>Powiązany licznik jest automatycznie aktualizowany tylko wtedy, gdy typ składnika majątku, z którym skojarzony licznik jest powiązany, istnieje w ustawieniach licznika. Na przykład: możesz skonfigurować licznik dla godzin produkcji i dodać typ składnika majątku „Silnik do samochodu ciężarowego”. Po zaktualizowaniu tego licznika powiązany licznik „Olej” jest również aktualizowany o te same wartości licznika. Konfiguracja w **licznikach** zawiera ustawienia „godziny”. Ponadto w liczniku „Olej” typ składnika majątku „Silnik do samochodu ciężarowego” należy dodać do skróconej karty **Typy składnika majątku**, aby zagwarantować relację licznika. Zobacz poniższe zrzuty ekranu, aby zapoznać się z przykładowymi ustawieniami liczników „Godziny” i „Olej”.

Gdy typy składników majątku zostaną dodane do typu licznika w obszarze **Liczniki**, ten licznik zostanie automatycznie dodany do typów składnika majątku na skróconej karcie **Liczniki**, zgodnie z opisem w temacie [Typy składników majątku](../setup-for-objects/object-types.md).

![Rysunek 1](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]