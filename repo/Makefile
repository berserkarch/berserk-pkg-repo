REPO_NAME = berserkarch-core

GPG_KEY_ID = B024DCEFADEF4328B5E3A848E7E0F2B78484DACF

REPO_DB = $(REPO_NAME).db
REPO_FILES = $(REPO_NAME).files
REPO_DB_SIG = $(REPO_DB).sig
REPO_FILES_SIG = $(REPO_FILES).sig

PKGS = $(wildcard *.pkg.tar.zst)

all: $(REPO_DB)

$(REPO_DB): $(PKGS)
	@echo "==> Removing old database and signature files..."
	rm -f $(REPO_DB) $(REPO_FILES) $(REPO_DB_SIG) $(REPO_FILES_SIG)

	@echo "==> Creating and signing repository database..."
	GPGKEY=$(GPG_KEY_ID) repo-add --sign --key $(GPG_KEY_ID) $(REPO_DB).tar.gz $(PKGS)

	@echo "==> Renaming database and signature to final names..."
	mv $(REPO_DB).tar.gz $(REPO_DB)
	mv $(REPO_DB).tar.gz.sig $(REPO_DB_SIG)
	mv $(REPO_FILES).tar.gz $(REPO_FILES)
	mv $(REPO_FILES).tar.gz.sig $(REPO_FILES_SIG)

clean:
	@echo "==> Cleaning up all repository files..."
	rm -f $(REPO_DB) $(REPO_FILES) $(REPO_DB_SIG) $(REPO_FILES_SIG)

.PHONY: all clean
