---
title: Lista produktów uwzględniających zapasy
description: W tym artykule opisano, w jaki sposób organizacje mogą konfigurować strony list produktów w witrynie sieci web portalu handlu elektronicznego rozwiązania Microsoft Dynamics 365 Commerce, tak aby uwzględniały one informacje o zapasach.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: 2a65dedf2da62fcd92169077d75a0f3b7832a86d
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473748"
---
# <a name="inventory-aware-product-listing"></a>Lista produktów uwzględniających zapasy

[!include [banner](../includes/banner.md)]

W tym artykule opisano, w jaki sposób organizacje mogą konfigurować strony list produktów w witrynie sieci web portalu handlu elektronicznego rozwiązania Microsoft Dynamics 365 Commerce, tak aby uwzględniały one informacje o zapasach. Strony list produktów zawierają strony docelowe kategorii i strony wyników wyszukiwania.

Klienci zazwyczaj oczekują, że znaleziony produktu w witrynie handlu elektronicznego będzie aktualną informacją na temat dostępności, tak aby mogli zdecydować, co zrobić, jeśli danego produktu brak w magazynie. Kategoria [Biblioteka modułów Commerce](starter-kit-overview.md) i moduły wyników wyszukiwania mogą być skonfigurowane, by uwzględniać dane zapasów. W ten sposób mogą zawierać następujące doświadczenia:

- Wyświetl etykiety na poziomie zapasów wraz z produktami.
- Ukryj produkty, których nie ma w magazynie, z listy produktów.
- Przenieś produkty, których nie ma w magazynie, na koniec stron list produktów.
- Obsługa filtrowania produktów opartych na zapasach.

Aby włączyć te doświadczenia, musisz najpierw włączyć cechę **Rozszerzone wykrywanie produktu handlu elektronicznego w celu otrzymania informacji o zapasach**, aby były one świadome zapasów w centrali Commerce headquarters.

> [!NOTE]
> Od wersji 10.0.29 Commerce i nowszych funkcja **Zwiększone wykrywanie produktów w handlu elektronicznym, aby były one świadome zapasów** jest domyślnie włączona.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Ustawianie atrybutu produktu dla dostępności zapasów

Lista produktów z informacjami o zapasach korzysta ze struktury atrybutów produktów. Wstępnie trzeba utworzyć wstępny, dedykowany atrybut produktu, aby można było przechwycić dane o dostępności zapasów.

Aby skonfigurować atrybut produktu dla dostępności zapasów w centrali Commerce headquarters, wykonaj poniższe kroki.

1. Przejdź do **Retail i Commerce \> Retail i Commerce — składniki IT \> Produkty i zapasy \> Wypełnij atrybuty produktu informacją o poziomie zapasów**.
1. W oknie dialogowym **Wypełnij atrybuty produktu informacją o poziomie zapasów** w polu **Atrybut produktu i nazwa typu** wprowadź niestandardową nazwę dedykowanego atrybutu produktu, który zostanie utworzony w celu przechwycenia danych zapasów.
1. W polu **Dostępność zapasów na podstawie** należy wybrać typ ilości, na podstawie której ma być obliczany poziom zapasów: **Dostępność fizyczna** lub **Wszystkie dostępne**.
1. W opcji **Przetwarzanie wsadowe** ustaw wartość **Tak**.
1. Kliknij przycisk **OK**.

> [!NOTE]
> Aby zapewnić spójne obliczanie poziomu zapasów na wszystkich stronach i modułach witryny handlu elektronicznego, upewnij się, aby wybrać ten sam typ ilości zarówno dla ustawienia **Dostępność zapasów na podstawie** dla zadania **Wypełnij atrybuty produktu poziomem zapasów**, jak i ustawienie **Poziom zapasów na podstawie** w kreatorze witryny Commerce.

Po utworzeniu dedykowanego atrybutu produktu następnym krokiem jest skonfigurowanie atrybutu dla kanału online.

Aby skonfigurować atrybut dla kanału online w centrali Commerce headquarters, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. Wybierz kanał internetowy, dla którego chcesz włączyć doświadczenie list produktów z informacjami o zapasach.
1. Wybierz i otwórz powiązaną grupę atrybutów, a następnie dodaj do niej nowy atrybut produktu.
1. Przejdź do **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji** i uruchom zadanie **1150** (**Katalog**). Zalecamy, aby również zaplanować to zadanie jako proces wsadowy, który będzie wykonywany z tą samą częstotliwością, co zadania **Wypełnij atrybuty produktu poziomem zapasów**.

> [!NOTE]
> W wersji Commerce 10.0.26 i wcześniejszej po dodaniu atrybutu produktu dostępności zapasów do grupy atrybutów trzeba również zaznaczyć **Ustaw metadane atrybutu**, a następnie włączyć opcję **Pokaż atrybut w kanale**, **Możliwe do pobrania**, **Mogą być uściślone** i **Można wykonać zapytania** dotyczące opcji nowego atrybutu produktu.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Skonfiguruj zachowanie wyświetlania produktów niedostępnych w magazynie na stronach listy produktów

Po ukończeniu wszystkich poprzednich kroków konfiguracji do udoskonalenia na stronach wyników wyszukiwania i kategorii będzie dostępna opcja filtru opartego na zapasach. Etykieta poziomu zapasów będzie wyświetlana dla każdego kafelka produktu wyświetlanego na stronie.

Na stronie wyników wyszukiwania i kategorii są wyświetlane produkty na poziomie głównym, a nie na poziomie wariantu produktu. Poziom zapasów wyświetlany obok każdego produktu jest zagregowanym poziomem zapasów, który zależy od poziomu zapasów wszystkich wariantów produktu. Poziom zapasów wariantu jest obliczany na podstawie dostępnych zapasów tego wariantu w domyślnym magazynie kanału online w centrali Commerce headquarters. Poziom zapasów produktu głównego ma dwie możliwe wartości reprezentujące stan dostępnych zapasów i stan braku w magazynie. Produkt główny jest uważany za wyczerpany wtedy, gdy wszystkie jego warianty są wyczerpane. W przeciwnym razie produkt jest uznany za dostępny w magazynie. Etykieta dla wartości jest pobierana z definicji [poziomu zapasów](inventory-buffers-levels.md). Jeśli nie określono poziomu zapasów, domyślne etykiety (w języku angielskim) to **Dostępne** i **Niedostępne w magazynie**.

Możesz skonfigurować ustawienie **Ustawienia zapasów dla stron list produktów** w kreatorze witryn Commerce, aby kontrolować sposób w jaki strony kategorii i wyników wyszukiwania są wyświetlane dla produktów niedostępnych w magazynie. Aby uzyskać więcej informacji, zobacz [Zastosuj ustawienia zapasów](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
