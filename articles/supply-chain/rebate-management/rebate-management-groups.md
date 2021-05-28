---
title: Zarządzanie rabatami — grupy
description: W tym temacie opisano sposób konfigurowania danych dla grup zarządzania rabatami. Grupy zarządzania rabatami mogą być używane podczas obliczania rabatów i mogą być dołączane do rekordu głównego.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: c9e1cadae97bd8f0dea270deaa1a8e09bb28eb4b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020490"
---
# <a name="rebate-management-groups"></a>Zarządzanie rabatami — grupy

[!include [banner](../includes/banner.md)]

Obliczenia rabatów i potrąceń mogą być oparte na grupach. Grupy zarządzania rabatami mogą być tworzone dla odbiorców, dostawców i towarów. Można je dołączyć do rekordu głównego.

## <a name="rebate-management-customer-groups"></a>Zarządzanie rabatami — grupy klientów

Obliczenia dla grupy odbiorców są często tworzone dla łańcucha firm, na przykład dla łańcucha supermarketów lub firmy. Ten typ obliczania jest zazwyczaj związany z rabatem.

Potrącenie jest często obliczane bez uwzględnienia tego, kto został sprzedany na podstawie kwalifikacji do zamówienia. Występują jednak pewne wyjątki. Na przykład, odbiorca może utworzyć schemat potrąceń, w którym grupa klientów A będzie otrzymywać 4 procent, a grupa odbiorcy B będzie otrzymywać tylko 3 procent.

### <a name="set-up-customer-groups"></a>Ustawianie grup odbiorców

Aby pracować z grupami klientów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy klientów**. Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb. Dla każdej grupy ustaw następujące pola:

- **Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.
- **Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.

### <a name="manage-customer-group-assignments"></a>Zarządzanie przypisaniami do grup klientów

Każdy odbiorca może należeć do dowolnej liczby grup zarządzania rabatami. Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy klientów.

Aby wyświetlić, dodać lub usunąć odbiorców z wybranej grupy, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabtami \> Grupy klientów**.
1. Wybierz grupę do zarządzania.
1. W okienku akcji wybierz **Klienci**. Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę odbiorców, którzy już są członkami wybranej grupy.
1. Aby dodać nowego klienta do grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Konto klienta**  - wybierz dowolne ID klienta.
    - **Nazwa** — wprowadź nazwę i/lub opis odbiorcy.

1. Aby usunąć klienta z grupy, wybierz klienta, a następnie wybierz polecenie **Usuń** w okienku akcji.

Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego klienta, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta, z którym chcesz pracować.
1. W okienku akcji, na karcie **Zarządzanie rabatami — umowy** w grupie **Obsługa** wybierz **Zmień stan**. Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany klient.
1. Aby dodać nowego klienta do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać odbiorcy.
    - **Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego odbiorca jest jej członkiem).

1. Aby usunąć klienta z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.

## <a name="rebate-management-vendor-groups"></a>Zarządzanie rabatami — grupy dostawców

Obliczenia dla grupy dostawców są często tworzone dla grupy punktów dostawy. Ten typ obliczania jest zazwyczaj związany z rabatem.

### <a name="set-up-vendor-groups"></a>Konfigurowanie grup dostawców

Aby pracować z grupami dostawców w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**. Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb. Dla każdej grupy ustaw następujące pola:

- **Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.
- **Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.

### <a name="manage-vendor-group-assignments"></a>Zarządzanie przypisaniami do grup dostawców

Każdy dostawca może należeć do dowolnej liczby grup zarządzania rabatami. Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy dostawców.

Aby wyświetlić, dodać lub usunąć dostawców z wybranej grupy, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy dostawców**.
1. Wybierz grupę do zarządzania.
1. W okienku akcji wybierz pozycję **Dostawcy**. Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę dostawców, którzy już są członkami wybranej grupy.
1. Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Konto dostawcy** - wybierz dowolne ID dostawcy.
    - **Nazwa** — wprowadź nazwę i/lub opis dostawcy.

1. Aby usunąć dostawcę z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.

Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego dostawcy, wykonaj następujące kroki.

1. Przejdź do pozycji **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**.
1. Wybierz dostawcy, z którym chcesz pracować.
1. W okienku akcji, na karcie **Dostawca** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**. Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany dostawca.
1. Aby dodać nowego dostawcę do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać dostawcy.
    - **Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego dostawca jest jej członkiem).

1. Aby usunąć dostawcę z grupy, wybierz grupy, a następnie wybierz polecenie **Usuń** w okienku akcji.

## <a name="item-rebate-groups"></a>Grupy rabatowe dla pozycji

Grupowanie towarów zapewnia większą elastyczność obliczania rabatów i potrąceń. Takie podejście często jest rozwiązaniem bardziej efektywnym w ustawianiu rabatów i potrąceń dla odbiorców i dostawców.

### <a name="set-up-item-groups"></a>Ustawianie grup pozycji

Aby pracować z grupami towarów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarów**. Możesz używać przycisków w Okienku akcji do dodawania, usuwania i edytowania grup w miarę potrzeb. Dla każdej grupy ustaw następujące pola:

- **Grupa zarządzania rabatami** – wpisz unikatową nazwę grupy rozmiarów.
- **Opis** — umożliwia wprowadzenie opisu grupy w celu zapewnienia większej liczby informacji na temat sposobu jej pracy.

### <a name="manage-item-group-assignments"></a>Zarządzanie przypisaniami do grup towarów

Każdy towar może należeć do dowolnej liczby grup zarządzania rabatami. Aby wyświetlić członków grupy i przypisać ich do nich, można rozpocząć od listy grup lub listy towarów. Można również dodawać elementy na podstawie hierarchii kategorii.

Aby wyświetlić, dodać lub usunąć towary z wybranej grupy, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.
1. Wybierz grupę do zarządzania.
1. W okienku akcji kliknij pozycję **Towary**. Zostanie wyświetlona strona **Grupy zarządzania rabatami** i pokazuje listę towarów, którzy już są członkami wybranej grupy.
1. Aby dodać nowego towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Konto towaru** - wybierz dowolne ID towaru.
    - **Nazwa produktu** — wprowadź nazwę i/lub opis towaru.

1. Aby usunąć towar z grupy, wybierz dostawcę, a następnie wybierz polecenie **Usuń** w okienku akcji.

Aby wyświetlić, dodać lub usunąć przypisania grupowe dla wybranego towaru, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz towar, z którym chcesz pracować.
1. W okienku akcji, na karcie **Produkt** w grupie **Zarządzanie rabatami — umowy** wybierz **Grupy zarządznia rabatami**. Pojawi się strona **Grupy zarządzania rabatami** i zawiera listę grup, do których należy już wybrany towar.
1. Aby dodać towar do nowej grupy, wybierz **Nowy** w okienku akcji, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Grupa zarządzania rabatami** — wybierz grupę, do których chcesz dodać towar.
    - **Opis** — służy do wprowadzania opisu grupy (na przykład w celu wyjaśnienia, dlaczego towar jest jej członkiem).

1. Aby usunąć towar z grupy, wybierz grupę, a następnie wybierz polecenie **Usuń** w okienku akcji.

Aby dodać towary do grupy na podstawie hierarchii kategorii, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie rabatami \> Ustawienia grup zarządzania rabatami \> Grupy towarow**.
1. Wybierz grupę do zarządzania.
1. W okienku akcji kliknij pozycję **Dodaj towary**.
1. W oknie dialogowym **Dodawanie towarów** w polu **Hierarchia kategorii** wybierz kategorię najwyższego poziomu.
1. Hierarchia towarów jest otwarta w lewym okienku. Wybierz poziom hierarchii, którego chcesz szukać. 
1. Elementy z wybranej hierarchii i poziomu hierarchii są teraz wyświetlane w prawym okienku. Aby pracować z tym okienkiem, należy wykonać następujące czynności:

    - Zaznacz pole wyboru przy każdym towarze, który chcesz dodać.
    - Zaznacz pole wyboru w nagłówku siatki, aby zaznaczyć wszystkie pozycje, które są wymienione.
    - Wybierz przycisk **Pokaż wybrane**, aby przefiltrować siatkę tak, aby wyświetlała tylko wybrane do tej pory elementy. Wybierz przycisk ponownie, aby powrócić do pełnej listy.

1. Wybierz przycisk **OK**, aby zastosować wybraną pozycję do wybranej grupy.
