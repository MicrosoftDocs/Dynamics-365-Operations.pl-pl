---
title: Automatyzacja procesu windykacji
description: W tym artykule opisano proces konfigurowania strategii procesu windykacji, która umożliwia automatyczne identyfikowanie faktur odbiorców wymagających przypomnienia w formie wiadomości e-mail, operacji windykacyjnej lub ponagleń wysyłanych do odbiorcy.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9ec749db197b4d04ee2e99ac7a16f4f2120c6707
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946186"
---
# <a name="collections-process-automation"></a>Automatyzacja procesu windykacji

[!include [banner](../includes/banner.md)]

W tym artykule opisano proces konfigurowania strategii procesu windykacji, która umożliwia automatyczne identyfikowanie faktur odbiorców wymagających przypomnienia w formie wiadomości e-mail, operacji windykacyjnej (np. rozmowy telefonicznej) lub ponagleń wysyłanych do odbiorcy. 

Organizacje często poświęcają znaczne ilości czasu na przeszukiwanie starych faktur, kont odbiorców oraz faktur bieżących, aby określić, z kim należy się kontaktować w sprawie nieopłaconej faktury lub salda konta. Proces ten zabiera wiele czasu, co zmniejsza możliwości pracownika, jeśli chodzi o komunikowanie się z klientami w celu zapłaty zaległych obciążeń lub rozwiązywanie sporów związanych z fakturowaniem. Automatyzacja procesu windykacji pozwala na skonfigurowanie w procesu gromadzenia danych podejścia opartego na strategii. Ułatwia to stosowanie działań windykacyjnych przez udostępnienie dostosowanych przypomnień pocztą e-mail lub zaprogramowanych procesów służących do wysyłania ponagleń. 

## <a name="collections-process-setup"></a>Konfiguracja procesu windykacji
Na stronie **Konfiguracja procesu windykacji** (**Kredyty i windykacja > Konfiguracja > Konfiguracja procesu windykacji**) można utworzyć zautomatyzowany proces windykacji, który będzie planować działania, wysyłać wiadomości e-mail oraz tworzyć i wysyłać listy ponaglające. Etapy procesu są oparte na pierwszej lub najstarszej nieopłaconej fakturze W każdym kroku wykorzystywana jest właśnie ta faktura w celu określenia, jaka komunikacja lub działanie ma być przeprowadzane względem danego klienta.  

Zespoły windykacji zwykle wysyłają wcześniejsze powiadomienie dotyczące każdej zaległej faktury, aby klient był powiadamiany o terminach płatności. Zaznaczenie opcji **Wstępnego duplikowania** można ustawić w taki sposób, aby zezwolić na działanie jednego kroku w każdej hierarchii procesów dla każdej faktury w czasie, do osiągnięcia tego etapu.

### <a name="process-hierarchy"></a>Hierarchia procesów
Każda pula klientów może być przypisana tylko do jednej hierarchii procesów. Ranga hierarchii w tym kroku określa, który proces będzie miał pierwszeństwo, jeśli klient zostanie uwzględniony w więcej niż jednej puli z przypisaną hierarchią procesów. Identyfikator puli określa, którzy klienci będą przypisani do procesu. Każda ustawiona hierarchia może być przypisana do tylko jednego procesu automatyzacji.

Funkcja „Dni bez kontaktu” służy do zapewnienia, że automatyczny kontakt z danym klientem nie będzie miał miejsca zbyt często. Jeśli na przykład wartość w funkcji „Dni bez kontaktu” wynosi dwa, odbiorca nie będzie kontaktowany przez proces zautomatyzowany przez co najmniej dwa dni, nawet jeśli oryginalna faktura wiodąca zostanie rozliczona w całości. 

Aby wykluczyć odbiorców z procesu automatyzacji, jeśli saldo wiekowania odbiorcy lub kwota faktury są mniejsze niż zdefiniowana wartość, wybierz wartość **Saldo wiekowania odbiorcy mniejsze niż** lub **Kwoty na fakturze mniejsze niż** w polu **Wyklucz z procesu** i wprowadź wartość kwoty.

Zaznacz **Użyj przewidywania**, by utworzyć działania kolekcji za pomocą Przewidywań płatności odbiorców. Utworzone działania będą używać szablonu działań **Przewidywań płatności** na stronie **Parametry modułu rozrachunków z odbiorcami**, karcie **Automatyzacja procesu windykacji**. 

### <a name="process-details"></a>Szczegóły procesu
Kliknij przycisk **Nowy**, aby dodać nowy szczegół procesu do hierarchii. **Opis** służy do identyfikowania celu lub nazwy etapu w hierarchii. Wybierz **Typ akcji**, by określić, czy etap, który utworzy działanie, ma wysłać wiadomość e-mail lub utworzyć ponaglenie. 

- **Dokument biznesowy** określa szablon używany do tworzenia typu akcji. Tym dokumentem może to być szablon działania, szablon wiadomości e-mail lub ponaglenie wysłane do każdego odbiorcy. Automatyzacja procesów windykacji powoduje tworzenie ponagleń dla każdego odbiorcy, niezależnie od konfiguracji innych parametrów windykacji.
- **Podczas** definiowania kroku procesu, który ma miejsce przed lub po dacie płatności wiodącej (najstarszej) faktury i używanej razem z liczbą wyświetlaną w kolumnie **Dni w odniesieniu do daty płatności faktury**. 
- Zaznacz opcję **Wstępne monitowanie**, aby utworzyć akcję dla każdej faktury w jednym kroku w hierarchii procesu. Działania wstępnego monitowanie to zwykle wcześniejsze powiadomienie dotyczące zaległej faktury, aby klient był powiadamiany o terminach płatności faktury. Wstępne monitowanie można zostać zaznaczone tylko dla jednego działania na hierarchię. Po wybraniu typu działania — wiadomość e-mail pole adresat będzie używane do określenia, czy wiadomość e-mail jest wysyłana do klienta, grupy sprzedażowej czy do agenta windykacji. 
- Wartość pola **Kontakt w celach biznesowych** określa, który kontakt z konta danego odbiorcy będzie otrzymywał wiadomości.

### <a name="business-document-details"></a>Szczegóły dokumentacji biznesowej
Szczegóły dokumentu biznesowego różnią się w zależności od typu działania wybranego w szczegółach procesu. Jeśli typem akcji jest działanie, zostaną wyświetlone szczegóły szablonu działania. Do tych szczegółów należą nazwa szablonu działania, typ działania, które zostanie utworzone, cel działania, liczba dni zaplanowanych do zakończenia działania oraz szczegóły działania. To działanie następnie przekieruje odbiorcę do faktury wiodącej, która informuje go o wymaganym działaniu.

Jeśli w szczegółach procesu typem akcji jest wiadomość e-mail, ta sekcja będzie zawierać dwie skrócone karty. Pierwsza służy do określenia identyfikatora szablonu, opisu wiadomości e-mail, domyślnego języka, nazwy użytkownika, która zostanie przypisana do wysyłanych automatycznie wiadomości e-mail oraz skojarzonych z nią adresów e-mail nadawców. Druga umożliwi utworzenie treści wiadomości e-mail po zapisaniu wartości w polach **Język** i **Temat** przez wybranie opcji **Edytuj**. Spowoduje to otwarcie okna umożliwiającego przesyłanie zawartości HTML. 

> [!Note]
> Możesz zapisać wiadomość e-mail programu Outlook zawierającą treść wiadomości w formacie HTML. Następnie możesz przekazać zawartość wiadomości, aby zaimplementować szablon. <br> <br> W przypadku wybrania typu akcji ponaglenie, na stronie ustawień nie pojawi się sekcja szczegółów dokumentu biznesowego.

Przycisk **Historia procesu windykacji** umożliwia wyświetlenie najnowszej historii wybranej hierarchii procesów. 

Kliknij akcję **Przypisanie procesu windykacji**, aby wyświetlić odbiorców przypisanych do procesu windykacji. Użyj opcji **Podgląd przypisania odbiorcy**, by wyświetlać hierarchię przypisaną do określonego odbiorcy. Użyj opcji **Podgląd przypisania procesu**, aby przejrzeć odbiorców, którzy zostaną przypisani do hierarchii po uruchomieniu. Kliknij opcję **Przypisanie ręczne**, by wyświetlać odbiorców ręcznie przypisanych do danego procesu lub wybranie opcji odbiorcy, którzy mają być przypisani do procesu.

Kliknij akcję **Przetwórz symulację**, by przejrzeć akcje, które zostaną utworzone, jeśli w tej chwili zostanie uruchomione wybrane automatyzacja procesów. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
