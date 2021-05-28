---
title: Tworzenie wstępnie zdefiniowanych wariantów produktu
description: Ta procedura prowadzi przez proces tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f78441445baecba279f96eb3935d9ebbb4ff03f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021915"
---
# <a name="predefined-product-variants"></a>Wstępnie zdefiniowane warianty produktu

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Przykładowy scenariusz: tworzenie wstępnie zdefiniowanych wariantów produktu

Ten przykładowy scenariusz pokazuje sposób tworzenia wariantów produktu dla produktu głównego przy użyciu kombinacji wymiarów produktu.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma *USMF*, aby móc użyć sugerowanych w przykładzie wartości.

### <a name="step-1-create-a-product-master"></a>Krok 1: tworzenie produktu głównego

Aby utworzyć produkt główny:

1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach > Produkty > Produkty główne**.
1. Wybierz pozycję **Nowy**.
1. Jeśli pole **Numer produktu** jeszcze nie zawiera numeru, wprowadź wartość. Ten krok jest wymagany tylko wtedy, jeśli żadna sekwencja numerów nie została skonfigurowana w tym polu.
1. W polu **Nazwa produktu** wprowadź nazwę.
1. W polu **Grupa wymiarów produktu** wybierz grupę wymiarów produktu *SizeCol* (Rozmiar i Kolor).
1. Wybierz przycisk **OK**, aby utworzyć i otworzyć nowy produkt główny.

### <a name="step-2-add-product-dimensions"></a>Krok 2: Dodawanie wymiarów produktu

W tym przykładzie pokazano, jak ręcznie wprowadzić wymiary produktu. Można także wybrać grupę rozmiaru, koloru lub stylu zawierającą wartości wymiarów produktu, których chcesz używać.

Aby dodać wymiary produktu:

1. Gdy nowy produkt główny jest nadal otwarty, wybierz opcję **Wymiary produktu** w okienku akcji.
1. Otwórz kartę **Rozmiar** i wybierz pozycję **Nowy** na pasku narzędzi, aby dodać wiersz do siatki. Dla nowego wiersza wprowadź następujące ustawienia:
    - **Rozmiar:** wybierz wartość rozmiaru.
    - **Nazwa**: wprowadź nazwę rozmiaru.
1. Wybierz pozycję **Nowy** na pasku narzędzi i dodaj drugi rozmiar do siatki z nową **nazwą** i **rozmiarem**.
1. Otwórz kartę **Kolory** i wybierz pozycję **Nowy** na pasku narzędzi, aby dodać wiersz do siatki. Dla nowego wiersza wprowadź następujące ustawienia:
    - **Kolor:** wybierz wartość koloru.
    - **Nazwa**: wprowadź nazwę koloru.
1. Wybierz pozycję **Nowy** na pasku narzędzi i dodaj drugi kolor do siatki z nowym **kolorem** i **rozmiarem**.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę, aby powrócić do nowego produktu głównego.

### <a name="step-3-generate-product-variants"></a>Krok 3: generowanie wariantów produktu

> [!NOTE]
> W tej sekcji opisano sposób generowania wariantów produktu, gdy funkcja *Ulepszenia strony wariantów sugestii* nie jest włączona. W następnej sekcji opisano, jak generować warianty produktów, gdy ta funkcja jest dostępna.

Aby generować warianty produktu:

1. Gdy nowy produkt główny jest nadal otwarty, wybierz opcję **Warianty produktu** w okienku akcji.
1. W okienku akcji wybierz pozycję **Sugestie wariantów**.
1. System wygeneruje listę ze wszystkimi możliwymi kombinacjami rozmiarów i kolorów zdefiniowanymi dla produktu. Wybierz opcję **Zaznacz wszystko** na pasku narzędzi.
    - W tym przykładzie wybierzesz wszystkie możliwe warianty. Aby użyć tylko podzbioru możliwych kombinacji wymiarów produktu, należy zaznaczyć tylko wymagane pola wyboru.  
1. Wybierz opcję **Utwórz**.
1. Wybierz opcję **Zapisz**.

## <a name="improved-variant-suggestions"></a>Ulepszone sugestie wariantów

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

Funkcja *Ulepszenia strony sugestii wariantów* usprawnia stronę **Sugestie wariantów**, aby rozwiązać problem z wydajnością i użytecznością w firmach, które mają wiele kombinacji wymiarów produktów. Rozszerzony proces wybierania wartości wymiarów produktu, dla których mają być generowane sugestie wariantów, ułatwia identyfikowanie i zwalnianie odpowiedniego zestawu wariantów produktów.

Ta funkcja dodaje następujące ulepszenia:

- **Odroczone generowanie sugestii wariantów:** strona **Sugestie wariantów** nie wyświetla już sugestii, gdy po raz pierwszy ją otwierasz. Należy jawnie wybrać wartości, które mają być potrzebne, a następnie wybrać przycisk **Sugeruj**, aby wygenerować kombinacje. Dzięki temu proces jest bardziej przewidywalny i interakcyjny.
- **Wybór wartości wymiarów:** jeśli istnieje wiele wartości wymiarów, zazwyczaj warto wygenerować sugestie wariantów, które obejmują tylko kilka z nich (na przykład przy tworzeniu nowego zestawu kolorów lub stylów). Dzięki ulepszonemu działaniu można wybrać wartości wymiarów, dla których mają być generowane sugestie wariantów produktu. Znacznie zwiększa to adekwatność sugerowanych wariantów oraz poprawia wydajność systemu i produktywność użytkowników.

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a>Włączanie funkcji ulepszeń strony Sugestie wariantów

Aby móc używać funkcji *Ulepszenia strony sugestii wariantów*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie informacjami o produktach*
- **Nazwa funkcji:** *ulepszenia strony Sugestie wariantów*

### <a name="work-with-the-improved-variant-suggestions"></a>Praca z ulepszonymi sugestiami wariantów

Aby generować sugestie wariantów produktu, gdy funkcja *Ulepszenia strony wariantów sugestii* jest włączona:

1. Otwórz lub utwórz produkt główny i dodaj do niego wymagane wymiary produktów, zgodnie z opisem w poprzedniej sekcji.
1. Gdy produkt główny jest nadal otwarty, wybierz opcję **Warianty produktu** w okienku akcji.
1. W okienku akcji wybierz pozycję **Sugestie wariantów**.
1. Wybierz wartości, których chcesz używać w poszczególnych wymiarach.
1. Na górnym pasku narzędzi wybierz pozycję **Sugeruj**.
1. System wygeneruje listę ze wszystkimi możliwymi kombinacjami wybranych rozmiarów i kolorów. Na skróconej karcie **Sugerowane warianty** zaznacz pole wyboru każdej kombinacji wymiarów produktu, której chcesz użyć, lub wybierz opcję **Zaznacz wszystko** na pasku narzędzi, aby zaznaczyć wszystkie z nich.  
1. Wybierz opcję **Utwórz**, aby dodać warianty do bieżącego produktu głównego.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
