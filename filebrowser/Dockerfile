FROM filebrowser/filebrowser:debian

# Set permissions for OpenShift deployment
RUN chgrp -R 0 /filebrowser && \
    chmod -R g+w /filebrowser && \
    chown -R 1001 /filebrowser

RUN chgrp -R 0 /.filebrowser.json && \
    chmod -R g+w /.filebrowser.json && \
    chown -R 1001 /.filebrowser.json

RUN chgrp -R 0 /srv && \
    chmod -R g+w /srv && \
    chown -R 1001 /srv

# RUN chgrp -R 0 /database.db && \
#     chmod -R g+w /database.db && \
#     chown -R 1001 /database.db

# RUN chgrp -R 0 "/"
# RUN chmod -R g+w "/"
# RUN chown -R 1001 "/"

USER 1001
