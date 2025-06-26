REPO_NAME = vigarch

REPO_DB = $(REPO_NAME).db
REPO_FILES = $(REPO_NAME).files

PKGS = $(wildcard *.pkg.tar.zst)

all: $(REPO_DB) $(REPO_FILES)

$(REPO_DB): $(PKGS)
	@echo "==> Initial cleaning..."
	rm -rf $(REPO_NAME).db $(REPO_NAME).files
	@echo "==> Creating repository database..."
	repo-add $(REPO_DB).tar.gz $(PKGS)
	rm -rf $(REPO_NAME).db $(REPO_NAME).files
	@mv $(REPO_DB).tar.gz $(REPO_DB)

$(REPO_FILES): $(REPO_DB)
	@mv $(REPO_FILES).tar.gz $(REPO_FILES)

clean:
	@echo "==> Cleaning up repository files..."
	rm -f $(REPO_DB) $(REPO_FILES) *.tar.gz

.PHONY: all clean
