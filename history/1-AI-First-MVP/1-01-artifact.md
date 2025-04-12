# Dokument wymagań produktu (PRD) - Aplikacja Gabinetu Akupunktury

## 1. Przegląd produktu

Aplikacja Gabinetu Akupunktury to system zarządzania wizytami online, zaprojektowany specjalnie dla gabinetów akupunktury. W wersji MVP aplikacja umożliwia rezerwację, anulowanie i zarządzanie wizytami pacjentów, z uwzględnieniem specyficznych potrzeb gabinetu akupunktury, takich jak różne czasy trwania wizyt (pierwszorazowa vs. kolejna).

Głównym celem aplikacji jest usprawnienie procesu rezerwacji wizyt, eliminacja błędów w harmonogramie oraz oszczędność czasu zarówno dla pacjentów, jak i dla pracowników rejestracji. System zapewnia dwustronną funkcjonalność - dla pacjentów oraz dla personelu gabinetu.

Aplikacja umożliwia pacjentom samodzielne rezerwowanie wizyt online bez konieczności logowania, a jednocześnie daje pracownikowi rejestracji pełny wgląd i kontrolę nad harmonogramem gabinetu.

## 2. Problem użytkownika

Obecnie ustalanie terminów wizyt pacjentów w gabinecie akupunktury jest procesem czasochłonnym i podatnym na błędy. Problemy, które napotykają użytkownicy, to:

- Konieczność telefonicznego umawiania wizyt, co wymaga dostępności personelu rejestracji
- Ręczne zarządzanie harmonogramem, co zwiększa ryzyko pomyłek i nakładających się wizyt
- Brak zautomatyzowanych przypomnień o wizytach, co prowadzi do nieobecności pacjentów
- Trudności w rozróżnianiu wizyt pierwszorazowych (2h) od wizyt kolejnych (1h)
- Czasochłonne zarządzanie notatkami i informacjami o pacjentach
- Brak możliwości samodzielnego anulowania wizyt przez pacjentów
- Trudności z planowaniem serii wizyt cyklicznych

MVP aplikacji adresuje te problemy poprzez zautomatyzowanie procesu rezerwacji, przypominania o wizytach oraz zarządzania terminarzem, co znacząco zmniejsza obciążenie personelu rejestracji i poprawia doświadczenie pacjentów.

## 3. Wymagania funkcjonalne

### 3.1 Zarządzanie pacjentami
- System rejestruje podstawowe dane pacjentów (imię, nazwisko, telefon, email, data urodzenia)
- Weryfikacja pacjenta odbywa się przez email/telefon
- System automatycznie tworzy profil nowego pacjenta, jeśli nie istnieje w bazie
- System umożliwia wyszukiwanie pacjentów przez pracownika rejestracji

### 3.2 Zarządzanie wizytami
- System umożliwia rezerwację wizyt przez pacjentów (bez logowania) i przez pracownika rejestracji
- System automatycznie rozpoznaje typ wizyty (pierwszorazowa 2h, kolejna 1h)
- System umożliwia anulowanie wizyty przez pacjenta do 24h przed terminem
- System pozwala pracownikowi rejestracji na zmianę statusu wizyty
- System oferuje możliwość planowania wizyt cyklicznych
- System umożliwia oznaczanie wizyt jako pilne lub specjalne
- System pozwala pracownikowi rejestracji na blokowanie terminów
- System umożliwia zarządzanie dniami wolnymi i godzinami pracy

### 3.3 Powiadomienia
- System wysyła potwierdzenia rezerwacji przez email/SMS
- System wysyła przypomnienia o wizytach 24h przed terminem przez email/SMS
- System generuje unikalny link do zarządzania wizytą w powiadomieniach

### 3.4 Kalendarz
- System prezentuje widok miesięczny z oznaczonymi dniami dostępności
- System oferuje widok dzienny dla pracownika rejestracji
- System stosuje kolorowe oznaczenia dla różnych typów wizyt
- System umożliwia filtrowanie według dostępnych godzin

### 3.5 Dokumentacja
- System umożliwia dodawanie notatek do wizyty i pacjenta
- System pozwala na załączanie plików do notatek
- System oferuje funkcję szybkich predefiniowanych notatek

## 4. Granice produktu

Następujące funkcje i elementy NIE są częścią MVP aplikacji:

- Aplikacja mobilna (na początek tylko wersja webowa)
- Integracja z systemami płatności online
- Generowanie faktur i rozliczenia finansowe
- Integracja z zewnętrznymi systemami medycznymi
- Rozbudowane funkcje raportowania i analityki
- System do zarządzania wieloma gabinetami jednocześnie
- Funkcjonalność dla wielu pracowników rejestracji (na start tylko jeden użytkownik)
- Zaawansowane funkcje marketingowe i program lojalnościowy
- Portal komunikacyjny między pacjentem a lekarzem

## 5. Historyjki użytkowników

### Zarządzanie pacjentami

#### US-001: Wyszukiwanie pacjenta
Jako pracownik rejestracji, chcę móc wyszukiwać pacjentów po imieniu, nazwisku, numerze telefonu lub adresie email, aby szybko znaleźć ich dane.

Kryteria akceptacji:
- System umożliwia wyszukiwanie po różnych kryteriach (imię, nazwisko, telefon, email)
- Wyniki wyszukiwania są prezentowane w formie listy
- Z listy wyników można przejść do pełnego profilu pacjenta
- System informuje, gdy nie znaleziono żadnych wyników

#### US-002: Dodawanie nowego pacjenta
Jako pracownik rejestracji, chcę móc dodać nowego pacjenta do systemu, aby zapisać jego dane do przyszłych wizyt.

Kryteria akceptacji:
- Możliwość wprowadzenia podstawowych danych pacjenta: imię, nazwisko, telefon, email, data urodzenia
- System waliduje wprowadzone dane (format email, telefonu)
- System informuje o pomyślnym dodaniu pacjenta
- System zapobiega duplikacji pacjentów przez sprawdzenie telefonu/email

#### US-003: Weryfikacja pacjenta przy rejestracji
Jako pacjent, chcę być zidentyfikowany przez system po podaniu numeru telefonu lub adresu email, aby nie musieć wprowadzać wszystkich danych za każdym razem.

Kryteria akceptacji:
- System pozwala na wprowadzenie numeru telefonu lub adresu email
- System identyfikuje istniejącego pacjenta lub prosi o uzupełnienie danych dla nowego
- System informuje o wyniku weryfikacji
- Istniejący pacjent może przejść do rezerwacji wizyty bez wprowadzania podstawowych danych

#### US-004: Edycja danych pacjenta
Jako pracownik rejestracji, chcę móc edytować dane pacjenta, aby aktualizować informacje kontaktowe.

Kryteria akceptacji:
- Możliwość edycji wszystkich pól danych pacjenta
- System waliduje wprowadzone zmiany
- System informuje o pomyślnej aktualizacji danych
- Historia zmian jest rejestrowana w systemie

### Zarządzanie wizytami

#### US-005: Rezerwacja wizyty przez pacjenta
Jako pacjent, chcę zarezerwować wizytę online, aby oszczędzić czas na telefonowanie do gabinetu.

Kryteria akceptacji:
- System pokazuje dostępne terminy w kalendarzu
- System blokuje terminy już zajęte lub poza godzinami pracy
- System automatycznie rozpoznaje typ wizyty (pierwsza/kolejna) i rezerwuje odpowiedni czas
- System wysyła potwierdzenie rezerwacji

#### US-006: Rezerwacja wizyty przez pracownika rejestracji
Jako pracownik rejestracji, chcę zarezerwować wizytę dla pacjenta, aby pomóc osobom, które wolą kontakt telefoniczny.

Kryteria akceptacji:
- Możliwość wyboru pacjenta z bazy lub dodania nowego
- Możliwość wyboru terminu z kalendarza
- Możliwość wyboru typu wizyty (pierwsza/kolejna)
- System potwierdza rezerwację i wysyła powiadomienie do pacjenta

#### US-007: Anulowanie wizyty przez pacjenta
Jako pacjent, chcę anulować wizytę online, aby nie musieć dzwonić do gabinetu.

Kryteria akceptacji:
- System umożliwia anulowanie wizyty za pomocą unikalnego linku z powiadomienia
- System blokuje możliwość anulowania mniej niż 24h przed wizytą
- System informuje o pomyślnym anulowaniu lub o braku takiej możliwości
- Zwolniony termin staje się dostępny dla innych pacjentów

#### US-008: Zarządzanie wizytą przez pracownika rejestracji
Jako pracownik rejestracji, chcę zarządzać statusami wizyt, aby śledzić ich realizację.

Kryteria akceptacji:
- Możliwość zmiany statusu wizyty (zaplanowana, odbyta, nieobecność, anulowana)
- Możliwość edycji terminu wizyty
- Możliwość anulowania wizyty (w dowolnym czasie)
- System rejestruje zmiany statusów i terminów

#### US-009: Planowanie wizyt cyklicznych
Jako pacjent, chcę zaplanować serię wizyt, aby nie musieć rezerwować każdej osobno.

Kryteria akceptacji:
- Możliwość wyboru częstotliwości wizyt (co tydzień, co dwa tygodnie, co miesiąc)
- Możliwość określenia liczby wizyt w serii
- System weryfikuje dostępność wszystkich terminów
- System informuje o pomyślnym zaplanowaniu serii lub o konfliktach

#### US-010: Blokowanie terminów przez pracownika rejestracji
Jako pracownik rejestracji, chcę blokować terminy w kalendarzu, aby uwzględnić przerwy i nieobecności.

Kryteria akceptacji:
- Możliwość blokowania pojedynczych godzin lub całych dni
- Możliwość określenia powodu blokady (nie widocznego dla pacjentów)
- Możliwość odblokowania wcześniej zablokowanych terminów
- Zablokowane terminy nie są dostępne do rezerwacji dla pacjentów

#### US-011: Oznaczanie wizyt specjalnych
Jako pracownik rejestracji, chcę oznaczać wizyty jako pilne lub specjalne, aby łatwo je rozróżniać.

Kryteria akceptacji:
- Możliwość oznaczenia wizyty jako pilnej lub specjalnej
- Możliwość dodania opisu specjalnego typu wizyty
- Specjalne wizyty są wyróżnione wizualnie w kalendarzu
- Możliwość filtrowania wizyt według typu

#### US-012: Ustawianie godzin pracy
Jako pracownik rejestracji, chcę ustawić standardowe godziny pracy gabinetu, aby pacjenci mogli rezerwować wizyty tylko w dostępnym czasie.

Kryteria akceptacji:
- Możliwość ustawienia godzin pracy dla każdego dnia tygodnia
- Możliwość ustawienia dni wolnych (np. święta)
- System blokuje rezerwacje poza godzinami pracy
- Możliwość tworzenia wyjątków od standardowych godzin

### Powiadomienia i komunikacja

#### US-013: Otrzymywanie potwierdzenia rezerwacji
Jako pacjent, chcę otrzymać potwierdzenie po dokonaniu rezerwacji, aby mieć pewność, że wizyta została zaplanowana.

Kryteria akceptacji:
- System wysyła potwierdzenie email po rezerwacji wizyty
- System wysyła potwierdzenie SMS po rezerwacji wizyty (jeśli podano telefon)
- Potwierdzenie zawiera datę, godzinę i typ wizyty
- Potwierdzenie zawiera unikalny link do zarządzania wizytą

#### US-014: Otrzymywanie przypomnienia o wizycie
Jako pacjent, chcę otrzymać przypomnienie przed wizytą, aby o niej nie zapomnieć.

Kryteria akceptacji:
- System automatycznie wysyła przypomnienie email 24h przed wizytą
- System automatycznie wysyła przypomnienie SMS 24h przed wizytą
- Przypomnienie zawiera datę, godzinę i informacje o lokalizacji gabinetu
- Przypomnienie zawiera link do zarządzania wizytą (anulowanie jeśli > 24h)

### Kalendarz i widoki

#### US-015: Przeglądanie kalendarza miesięcznego
Jako pacjent, chcę zobaczyć miesięczny widok kalendarza, aby wybrać dogodny dzień na wizytę.

Kryteria akceptacji:
- Kalendarz pokazuje bieżący miesiąc z możliwością nawigacji (poprzedni/następny)
- Dni z dostępnymi terminami są wyraźnie oznaczone
- Dni poza godzinami pracy lub dni wolne są oznaczone jako niedostępne
- Kliknięcie na dzień pokazuje dostępne godziny

#### US-016: Przeglądanie harmonogramu dziennego
Jako pracownik rejestracji, chcę zobaczyć dzienny widok harmonogramu, aby zarządzać wizytami w danym dniu.

Kryteria akceptacji:
- Widok pokazuje wszystkie wizyty w formie osi czasu
- Wizyty są kolorowo oznaczone według statusu/typu
- Widoczne są informacje o pacjencie przy każdej wizycie
- Możliwość nawigacji między dniami

#### US-017: Dostęp do historii wizyt pacjenta
Jako pacjent, chcę zobaczyć historię moich wizyt, aby mieć wgląd w mój plan leczenia.

Kryteria akceptacji:
- System umożliwia dostęp do historii po weryfikacji email/telefon
- Historia pokazuje daty, godziny i statusy wizyt
- Historia nie pokazuje notatek lekarza/pracownika
- Możliwość sortowania i filtrowania historii

#### US-018: Przeglądanie historii wizyt pacjenta przez pracownika
Jako pracownik rejestracji, chcę przeglądać historię wizyt pacjenta, aby mieć pełny wgląd w jego plan leczenia.

Kryteria akceptacji:
- Możliwość wyboru pacjenta i wyświetlenia jego historii wizyt
- Historia pokazuje daty, godziny, statusy wizyt i notatki
- Możliwość sortowania i filtrowania historii
- Możliwość przejścia z historii do szczegółów konkretnej wizyty

### Dokumentacja

#### US-019: Dodawanie notatek do wizyty
Jako pracownik rejestracji, chcę dodawać notatki do wizyt, aby zapisać ważne informacje.

Kryteria akceptacji:
- Możliwość dodania, edycji i usunięcia notatki do wizyty
- Możliwość załączania plików do notatki
- Notatki są widoczne tylko dla pracownika rejestracji
- System zapisuje autora i czas utworzenia/modyfikacji notatki

#### US-020: Dodawanie notatek do profilu pacjenta
Jako pracownik rejestracji, chcę dodawać notatki do profilu pacjenta, aby zapisać ogólne informacje o pacjencie.

Kryteria akceptacji:
- Możliwość dodania, edycji i usunięcia notatki do profilu pacjenta
- Możliwość załączania plików do notatki
- Notatki są widoczne tylko dla pracownika rejestracji
- System zapisuje autora i czas utworzenia/modyfikacji notatki

#### US-021: Używanie szybkich notatek
Jako pracownik rejestracji, chcę używać predefiniowanych szablonów notatek, aby oszczędzić czas.

Kryteria akceptacji:
- Dostępna lista predefiniowanych szablonów notatek
- Możliwość wyboru szablonu i dodania go do notatki
- Możliwość modyfikacji tekstu po wybraniu szablonu
- Możliwość tworzenia nowych szablonów

### Uwierzytelnianie i autoryzacja

#### US-022: Logowanie do panelu administracyjnego
Jako pracownik rejestracji, chcę bezpiecznie logować się do panelu administracyjnego, aby zarządzać wizytami i pacjentami.

Kryteria akceptacji:
- System wymaga podania nazwy użytkownika i hasła
- System stosuje bezpieczne metody przechowywania haseł
- System blokuje konto po wielokrotnych nieudanych próbach logowania
- System umożliwia odzyskanie dostępu w przypadku zapomnienia hasła

#### US-023: Zarządzanie dostępem do danych pacjenta
Jako pracownik rejestracji, chcę mieć pewność, że dane pacjentów są bezpieczne i dostępne tylko dla autoryzowanych osób.

Kryteria akceptacji:
- Dostęp do danych pacjentów wymaga uwierzytelnienia
- System loguje wszystkie próby dostępu do danych
- System umożliwia wylogowanie z panelu administracyjnego
- System automatycznie wylogowuje użytkownika po okresie nieaktywności

## 6. Metryki sukcesu

### 6.1 Metryki ilościowe
- Zmniejszenie czasu poświęcanego na telefoniczną obsługę rezerwacji o minimum 30%
- Zmniejszenie liczby nieobecności pacjentów o minimum 20% dzięki automatycznym przypomnieniom
- Minimum 50% nowych rezerwacji dokonywanych online przez pacjentów
- Minimum 90% poprawnie rozpoznanych i przydzielonych typów wizyt (pierwsza/kolejna)
- Minimum 95% dostępność systemu w godzinach pracy gabinetu

### 6.2 Metryki jakościowe
- Pozytywne opinie pacjentów dotyczące łatwości rezerwacji wizyt online
- Zadowolenie pracownika rejestracji z funkcjonalności zarządzania harmonogramem
- Zmniejszenie liczby błędów w harmonogramie (nakładające się wizyty, niewłaściwe czasy trwania)
- Zwiększenie satysfakcji pacjentów z procesu rezerwacji i przypominania o wizytach
- Skuteczna dokumentacja wizyt i pacjentów poprzez system notatek

### 6.3 Długoterminowe wskaźniki sukcesu
- Zwiększenie liczby wizyt dzięki efektywniejszemu zarządzaniu harmonogramem
- Zwiększenie retencji pacjentów dzięki lepszej obsłudze i komunikacji
- Rozszerzenie funkcjonalności systemu na podstawie zebranych danych i opinii użytkowników
- Potencjalne wdrożenie aplikacji mobilnej w kolejnej fazie rozwoju